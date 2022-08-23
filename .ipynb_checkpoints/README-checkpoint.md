# Quantum Natural Language Processing with lambeq --> by Quantinuum

Womanium Quantum Hackathon 2022

## Data:

- **Challenge Name**: Quantum Natural Language Processing with lambeq (Quantinuum)
- **Team Name**: Quriosity
- **Team**:
  - Tessa Evers -> Github: everstessa1, Email: everstessa1@gmail.com, Discord ID: TE#8644
  - Gehad Salem -> Github: GehadSalemFekry, Email: GehadSalemFekry@aucegypt.edu, Discord ID: Gehad Salem#7458
  - Tariq Islam -> Github: TariqAnt, Email: tariqquant@gmail.com, Discord ID: tariq_self#6191
  - Adhish V S -> Github: Adhish08, Email: v.s.adhish8@gmail.com, Discord ID: Adhish V S#0024
  - Sylvester Kabiru -> Github: Sylvester96, Email: sylvesterkbr@gmail.com, Discord ID: Sylvester#3016
  - Etendra Verma -> Github: etendra2501, Email: etendraverma2501@gmail.com
- **Pitch Presenter**: Tessa Evers

## Summary:

The goal of the project is to create a quantum model that takes two sentences and responds with the similarity between them (1 for similar, 0 for not similar), and similarity is defined to be as being of the same topic. The data provided was only using statements either related to `food` or `it`, but the model could then be extended when having a larger dataset with different topics.

We first tried to get a general overview of the data and what are its different characteristics; we used the `wordcloud` package to visualize the data based on the frequency of the different words presented to get a general idea of what is included and what to expect.

After that, we parsed the sentences into diagrams; we chose the `BobcatParser` from `lambeq` as it is a parser so has some grammar rules built in, unlike other readers that only read data into diagrams without any grammar linked to the diagrams. 

Then, we transformed the diagrams into circuits using `IQPAnsatz` while also removing cups in the diagrams to reduce the number of computations so, increasing the performance of the model.

In this stage, we were in need of a model that could perform the sentence comparison, so we built our own by inheriting from `NumpyModel` and editing its forward function by adding a similarity metric (an inner product for both sentences. Additionally, we defined the `loss` and `accuracy` metrics needed for training the model.

Then, we trained the model over a portion of the dataset (`80%`)  so to validate and test with the other `20%`. And at the end visualized the results we got from the training.

**Future improvements:**
- Create circuit reader function that is able to read each element but then we include it in the opposite order.
- Implement a better similarity metric.
- Train the model using `AerBackend`
- Having a bigger dataset
