##  An action

    export default fluxApp.registerActions('posts', {
      getAll() {
        return this.context.fetcher({ url: '/api/posts' });
      },

      get(id) {
        return this.context.fetcher({ url: '/api/posts/' + id });
      },

      delete: (id) => {
        return this.context.fetcher({
          url: '/api/posts/' + id,
          method: 'DELETE'
        });
      },
      ...

