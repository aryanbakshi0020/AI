# AI
Task 1
from sumy.parsers.plaintext import PlaintextParser
from sumy.nlp.tokenizers import Tokenizer
from sumy.summarizers.lsa import LsaSummarizer  

def summarize_text(text, sentence_count=5):
  
    parser = PlaintextParser.from_string(text, Tokenizer("english"))
    summarizer = LsaSummarizer()

   
    summary = summarizer(parser.document, sentence_count)

    
    print("\n--- Summary ---")
    for sentence in summary:
        print(sentence)


article = """
Artificial intelligence (AI) is transforming industries by enabling machines to perform tasks that 
traditionally require human intelligence. From speech recognition and decision-making to visual perception, 
AI is becoming increasingly prevalent. Its applications span healthcare, finance, transportation, and more. 
While AI promises great benefits such as improved efficiency and cost savings, it also raises concerns 
around ethics, job displacement, and data privacy. Experts emphasize the importance of transparent and 
responsible development of AI technologies.
"""

summarize_text(article, sentence_count=3)
AI automates tasks, boosts efficiency, spans industries—yet raises ethics, job loss, and privacy concerns.
