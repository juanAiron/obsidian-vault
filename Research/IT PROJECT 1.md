
Desired - Mobile Application (for now?)

Pre-Trained Model (Venipuncture) -  

Dataset 
ETS & Syringe

Data flow - Diagram



**Questions to be asked**
1. Needs ng Proponent
	1. detailed needs - automate feedback
	2. 
2. Why RAG? Why not use other frameworks like Fine-Tuning or Long Context Windows
	Tools and Technologies
		1. Javascript
		2. CSS
3. Why use Ollama as an AI engine?
4. Will Visual Studio Suffice?
5. Why React? Vite, Jest ease  FARM Stack 
6. Why Chroma DB? 
7. Why Python, Fast API?
8. Why PostreSQL
9. Why Nginx?
	1. **Nginx's Edge:** NGINX was built to solve the "C10k problem" (handling 10,000 concurrent connections). It uses an **event-driven architecture**, whereas Apache traditionally uses a "process-per-connection" model.
10. NGINX is not just a web server; it is a world-class **Reverse Proxy**.
	1. A Forward Proxy sits in front of a group of **clients** (users). When those users send requests to the internet, the request goes through the proxy first. The internet sees the IP address of the proxy, not the individual users.

- **Primary Goal:** To hide the identity of the user or to bypass network restrictions.
A Reverse Proxy sits in front of a group of **web servers** (like your FastAPI backend). When a user sends a request to your website, they talk to the Reverse Proxy. The proxy then decides which internal server should handle the request.

- **Primary Goal:** To protect the servers, balance the load, and improve performance.

It hides the internal ports of your database/AI.

RAG Pipeline
yung Vector Database