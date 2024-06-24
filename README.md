# Huggingface
treinando
// Programatically interact with the Hub

await createRepo({
  repo: {type: "model", name: "my-user/nlp-model"},
  credentials: {accessToken: HF_TOKEN}
});

await uploadFile({
  repo: "my-user/nlp-model",
  credentials: {accessToken: HF_TOKEN},
  // Can work with native File in browsers
  file: {
    path: "pytorch_model.bin",
    content: new Blob(...) 
  }
});

// Use hosted inference

await inference.translation({
  model: 't5-base',
  inputs: 'My name is Wolfgang and I live in Berlin'
})

await inference.textToImage({
  model: 'stabilityai/stable-diffusion-2',
  inputs: 'award winning high resolution photo of a giant tortoise/((ladybird)) hybrid, [trending on artstation]',
  parameters: {
    negative_prompt: 'blurry',
  }
})
