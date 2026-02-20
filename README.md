export default {
  async fetch(request, env) {
    const url = new URL(request.url);
    url.hostname = 'api.anthropic.com';
    const newRequest = new Request(url.toString(), {
      method: request.method,
      headers: request.headers,
      body: request.body
    });
    return fetch(newRequest);
  }
}
