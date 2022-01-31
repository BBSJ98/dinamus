# dinamus
integração de pedidos
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "[\"Product\"][\"ean\"]=98799979789879&[\"Product\"][\"name\"]=Produto Teste API&[\"Product\"][\"description\"]=Descrição do Produto de Teste da API&[\"Product\"][\"description_small\"]=Produto de Teste da API&[\"Product\"][\"price\"]=10.01&[\"Product\"][\"cost_price\"]=10.01&[\"Product\"][\"promotional_price\"]=10.01&[\"Product\"][\"start_promotion\"]=2019-04-01&[\"Product\"][\"end_promotion\"]=2019-04-30&[\"Product\"][\"brand\"]=Marca&[\"Product\"][\"model\"]=Modelo&[\"Product\"][\"weight\"]=1000&[\"Product\"][\"length\"]=10&[\"Product\"][\"width\"]=10&[\"Product\"][\"height\"]=10&[\"Product\"][\"stock\"]=100&[\"Product\"][\"category_id\"]=2&[\"Product\"][\"available\"]=1&[\"Product\"][\"availability\"]=Disponível em 3 dias&[\"Product\"][\"availability_days\"]=3&[\"Product\"][\"reference\"]=111&[\"Product\"][\"hot\"]=1&[\"Product\"][\"release\"]=1&[\"Product\"][\"additional_button\"]=0&[\"Product\"][\"related_categories\"]=[3,5,7]&[\"Product\"][\"release_date\"]=\"\"&[\"Product\"][\"shortcut\"]=\"\"&[\"Product\"][\"virtual_product\"]=0");
Request request = new Request.Builder()
  .url("{{api_address}}/products?access_token={{access_token}}")
  .method("POST", body)
  .addHeader("Content-Type", "application/x-www-form-urlencoded")
  .build();
Response response = client.newCall(request).execute();
