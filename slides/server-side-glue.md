##  Server side glue

    function appHandler(request, reply) {
      const context = fluxApp.createContext({
        fetcher: fetcher('hapi', {
          request,
        }),
        getUser: () => request.auth.credentials,
      });

      context.getRouterActions().init(request.path, {
        method: request.method,
      });

      return context.getPageContext(request.path, {
        method: request.method,
        dehydrate: true,
        wait: true,
      }).then(page => {
        const markup = page.element ? React.renderToString(page.element) : void(0);

        if (! markup) {
          throw Boom.notFound();
        } else {
          reply(Mustache.render(indexTemplate, {
            ...
