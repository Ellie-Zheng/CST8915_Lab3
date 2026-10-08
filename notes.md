# CST8915 Lab 3 - CST8915 Full-stack Cloud-native Development: Deploying the Algonquin Pet Store on Azure

- **Student Name**: Ellie Zheng
- **Student ID**: 041078727
- **Course**: CST8915 Full-stack Cloud-native Development
- **Semester**: Fall 2026

---

## Notes About Setup Challenges

The first step I worked on in this lab was rewriting the Product Service from Rust to Python. I tested the new `/products` endpoint locally, and it returned the correct product data, so I thought the rewrite was complete. Later, while working through the rest of the lab and reviewing the instructor's materials, I came across his public product-service-L3P repository. I compared its Python code with mine line by line and noticed that my version did not include python-dotenv or flask-cors. I then added them to support loading local .env settings and allowing the browser-based Store Front to request products from a different origin. This taught me that a successful local API test does not confirm that a rewritten service is ready to integrate with the rest of the application.

## References

- [Mohamed, R. product-service-L3P. GitHub](https://github.com/ramymohamed10/product-service-L3P)
