
In this simple case, we will work with AI Gemini, we will better understand how Embbeding works so that we can include it in a vector database.


![ThumbsUpDoubleThumbsUpGIF (2)](https://github.com/Tiagoribeirorp/Gemini-API-study-case/assets/24392536/65b8c466-0551-49fe-a160-6a0a19f1c90a)




## Gemini-API-study-case
### For all they want learn how call embedding gemini api to simple project


### first of all: install the "google-generative ai"

pip install google-generativeai

### after, import os and google.generativeai
import google.generativeai as genai
import os

### And call your gemini api
os.environ['GOOGLE_API_KEY'] = "your gemini api"
genai.configure(api_key = os.environ['GOOGLE_API_KEY'])


### now we have to work in our code, to "embendding' our first world!
result = genai.embed_content(
    model="models/embedding-001",
    content="cat",
    task_type="retrieval_document",
    title="Embedding of single string")
print(str(result['embedding']))

### A Lot of vector's from the world cat"

[0.014542307, 0.0006178697, -0.020780778, -0.055026993, 0.023107953, 0.018338924, 0.035312396, -0.037551843, -0.011747273, 0.033963777, 0.020098517, 0.018110545, -0.026435172, -0.019460762, -0.020371746, -0.013689507, 0.05151474, 0.017065361, -0.032209445, -0.035220638, 0.014930037, -0.016399246, 0.017805962, -0.0011097102, 0.006844126, -0.018118314, 0.0703797, -0.042333104, -0.01760461, 0.0253717, -0.011371508, 0.015451267, -0.06349474, -0.003772016, 0.014191814, -0.012418818, -0.017419312, -0.044079237, -0.027457776, 0.035718158, 0.03479573, -0.044851243, -0.0069242488, -0.04645494, 0.041640073, 0.0017240846, 0.027826501, 0.034774914, 0.008754955, -0.07618798, 0.03891449, 0.0035262173, 0.09418147, -0.034309346, -0.023647398, -0.024688672, 0.020739611, -0.008700395, -0.044575687, -0.027159281, 0.036582008, 0.00069796195, 0.007754381, 0.040094096, -0.0014853744, -0.039270222, -0.07998385, 0.079917856, 0.027102621, -0.027016524, 0.008836334, -0.025293155, 0.027449548, 0.019888947, -0.02753283, -0.06819163, -0.0054338975, 0.01927949, 0.0019765093, -0.0034976425, 0.054359023, -0.024291528, -0.031884063, -0.008366786, -0.053955752, 0.030560931, -0.044360362, -0.020957502, -0.007031724, 0.03411061, 0.019979412, -0.0097378995, -0.0023949265, -0.038721487, -0.0123324, 0.041301124, 0.008188205, -0.0040807016, -0.0047996435, 0.011745905, 0.019276952, -0.005771554, -0.04731476, 0.04173812, 0.044666108, 0.013753335, 0.038533304, 0.09679273, 0.004440452, 0.0039764866, -0.027454171, -0.0569166, -0.010861626, 0.010818206, 0.010137404, 0.003715917, 0.029666817, 0.044942215, 0.041140895, -0.016901335, -0.0025009129, 0.0077182804, 0.07127664, 0.01394554, -0.014866622, 0.00928493, -0.013959875, 0.030311914, 0.017434573, 0.03330224, -0.018071758, -0.071630284, 0.01539008, 0.01529485, 0.08417809, 0.077


### now we will work with some words to classify them and we will put a limit

result1 = genai.embed_content(
    model="models/embedding-001",
    content=[
      'cat',
      'dog',
      'duck'],
    task_type="retrieval_document",
    title="Entendendo embedding")

### A list of inputs > A list of vectors output
for v in result1['embedding']:
  print(str(v)[:50], '... Limite ...')

  [0.023736604, -0.011225404, -0.05085168, -0.033844 ... Limite ...
[0.036998272, -0.0137494905, -0.049106725, 0.00448 ... Limite ...
[0.030025821, -0.04013281, -0.076033466, -0.003369 ... Limite ...


  
