##  Client side glue

    let context = fluxApp.createContext({
      fetcher: require('fluxapp-fetch')('jquery'),
    });

    const routerActions = context.getRouterActions();

    function render(page) {
      React.render(
        page.element,
        appElement
      );
    }

    context.registerRouteHandler(function routeHandler(request) {
      const isFirstRequest = ! request.lastRequest;
      let options = {
        wait: true,
      };

      if (isFirstRequest) {
        options = {
          wait: false,
          noLoader: true,
          state: serverState.state,
        };
      }

      context.getPageContext(request, options).then(render);
    });

    routerActions.init(window.location.href, {
      method: serverState.metod,
    });

