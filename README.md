# SBLAD Corpus

Dialogue from 26 AI-generated scenario-based learning and assessments (SBLAs), built with the MEOW authoring system. It accompanies the paper *Recurring Lexical Patterns in AI-Generated Dialogue for Scenario-Based Learning and Assessment* (Suhan, Hoang, Wang, Guo, & O'Reilly).

Each SBLA was generated from the same prompt and one open-licensed (CC BY / CC BY-SA) textbook chapter. The corpus has 638 dialogue turns and 14,901 tokens. It includes scripted dialogues and pre-seeded messages for the interactive AI chat component.

## Files

| Path | Contents |
|---|---|
| `SBLAD_corpus.csv` | One row per dialogue line: `content_id`, `speaker`, `text`, position in the dialogue and the assessment, block type, and edit metadata |
| `corpus_document_list.xlsx` | The 26 SBLAs in the corpus |
| `keyness/` | Log-likelihood (G²) results for SBLAD against OpenSubtitles2018, AMI, and MICASE. The `_docfreq2_` files hold 2–4-grams that occur in at least 2 SBLAs, at p < .001 |

## Method

Text is split into sentences, tokenized with spaCy, lowercased, and stripped of punctuation. n-grams are formed within sentences. G² (Rayson & Garside, 2000) compares n-gram frequencies against each reference corpus, with a cutoff of G² > 10.83.

Of 93 4-grams that recur in at least 2 SBLAs, 77 are overrepresented against at least one reference corpus.

## Notes

- The reference corpora are not included. Get them from OpenSubtitles2018, AMI, and MICASE.
