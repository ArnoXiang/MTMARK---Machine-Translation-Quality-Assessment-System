# MTMARK---Machine-Translation-Quality-Assessment-System

## Introduction

MTMARK is a self-developed translation quality evaluation tool designed to assist in the assessment of machine translation. It supports parallel analysis of multiple segments of text in conjunction with reference translations. The tool automatically outputs BLEU scores and MQM evaluation reports for each segment and provides data visualization. Additionally, it can generate reports in Word document format. The evaluation results are more intuitive and comprehensive, allowing users to compare the quality of multiple machine translations side by side. Although the MQM analysis results may occasionally contain errors due to the randomness of GPT-generated content, the final judgment results are highly similar to those obtained through manual review.

## Authors

Xiang Yizhuo, Qi Hao, Zheng Chuyi, Zhang Siyi  
Beijing Language and Culture University, Translation (Localization) Program, Class of 2021

## Explanation of Translation Evaluation Standards Used (GEMBA-MQM, BLEU)

1. GEMBA-MQM
   When using MQM to evaluate machine translation quality, some obvious evaluation errors and inaccuracies were encountered. This practice is mainly based on GPT-4 for evaluation. Due to the inherent uncertainty of the model, we found that the final evaluation results also showed some uncertainty. Although the probability of errors caused by this uncertainty is very small and often beyond our control, we should be aware of the existence of such issues. The major types of errors encountered in our practice include but are not limited to:

   - Mistranslation Evaluation Errors: MQM often erroneously identifies correct translations as mistranslations, especially in the evaluation of specific domain terms in fields such as economics and finance, and in complex expressions. The system frequently mistook correct translations for errors, resulting in unusually low MQM scores.
   - Omission Evaluation Errors: MQM repeatedly misidentified certain parts of the translation as missing, even though those parts were correctly translated in the actual translation.
   - Semantic Understanding Errors: The system exhibited deviations in understanding the semantics of complex sentences, leading to minor errors being misjudged as severe errors.
     Due to the uncertainty in GPT model generation, MQM displayed a certain level of inconsistency in evaluation results. The same sentence could yield different results in different evaluations. Overall, MQM performed poorly when dealing with sentences containing specialized terminology and complex syntax. The evaluation results require further manual optimization to improve reliability and accuracy.

2. BLEU
   The BLEU evaluation method is a commonly used metric for assessing machine translation quality, primarily measuring the similarity between the translation and the reference translation. BLEU evaluates translation quality by calculating the number of n-gram matches (where n-gram can be words, phrases, or short sentences) between the translation and the reference translation.
   Researchers have found that BLEU scores are highly correlated with the fluency of the translation and the precise matching of vocabulary and phrases. This means that the more similar the vocabulary and phrases used in the translation are to the reference translation, the higher the BLEU score. However, BLEU does not directly assess the semantic accuracy and coherence of the translation; it only indirectly reflects translation quality through surface-level vocabulary matching.
   Our practice results indicate that BLEU scores show high correlation in measuring translation fluency, which aligns with the conclusions obtained using the MTMARK tool. Therefore, BLEU scores can serve as an effective metric for evaluating translation quality, especially in terms of fluency and matching. Although BLEU may not fully reflect the quality of the translation in some cases, it still holds reference value and can be combined with other quality evaluation standards to conduct a multidimensional assessment of translation quality. This helps researchers more accurately measure the performance of machine translation tools.

## Usage Instructions

1. Refer to [fix: use Fraction override · nltk/nltk@86fa083](https://github.com/nltk/nltk/commit/86fa0832f0f4b366f96867f59ae05d744d68b513) to fix the native BLEU implementation in the NLTK library.
2. Ensure that the utils directory is extracted in the same directory as main.py to run the Youdao Translation API.
3. If the output report is not in the current program directory, please check the user folder.
4. Due to issues related to the Python Docx library, there may be font display errors; please change the Word font.
5. Replace all strings starting with APIKEY with your own API key.
