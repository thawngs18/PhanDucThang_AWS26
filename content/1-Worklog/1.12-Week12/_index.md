---
title: "Week 12 Worklog"
date: 2026-01-01
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* Deploy the frontend to AWS using S3 and CloudFront.
* Complete the frontend-backend connection and ensure CORS works end to end.
* Integrate AI services with Gemini and verify the full feature workflow.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Build the CloudNexus-Secrets stack: create Secrets Manager and store `GOOGLE_API_KEY` <br> - Build the CloudNexus-Backend stack: create Lambda function with FastAPI through Mangum, HTTP API Gateway, and IAM roles <br> - Configure a Lambda Layer with Python dependencies including FastAPI, Mangum, and Google Generative AI <br> - Perform the first deployment of both stacks to AWS <br> - Initialize the frontend structure with Vite, React, React Flow, Zustand, and TailwindCSS <br> - Configure the build script for frontend deployment to S3 <br> - Deploy the S3 bucket and set up CloudFront distribution for the frontend | 06/06/2026 | 06/06/2026 | <https://docs.aws.amazon.com/cdk/api/v2/python/> <br> <https://docs.python.org/3/library/asyncio.html> <br> <https://github.com/jmaddock/lambda-pipeline> |
|| 3   | - Fix CORS preflight OPTIONS requests from CloudFront returning 400 Bad Request from API Gateway <br> - Remove CORS configuration from API Gateway to avoid double handling with FastAPI CORSMiddleware <br> - Add an `@app.options` handler in FastAPI to handle preflight requests <br> - Update `allow_origins` in CORSMiddleware with the CloudFront URL and localhost <br> - Add a new Lambda Layer with all required dependencies <br> - Rebuild and redeploy the Lambda function | 07/06/2026 | 07/06/2026 | <https://vitejs.dev/guide/build> <br> <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html> |
|| 4   | - Configure `VITE_API_URL` in `.env.production` to point to the production API Gateway endpoint <br> - Set up the build configuration for Vite production mode <br> - Redeploy the built frontend bundle to S3 and invalidate CloudFront cache <br> - Verify the connection from the CloudFront frontend to the backend API | 08/06/2026 | 08/06/2026 | <https://fastapi.tiangolo.com/tutorial/first-steps/> <br> <https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS> |
|| 5   | - Complete the FastAPI backend by adding a GET `/` endpoint that returns API metadata <br> - Verify all endpoints run correctly: `/api/health`, `/api/ai/generate`, `/api/topology/validate`, and `/api/simulation/scan` <br> - Check CORS headers on all endpoints from the CloudFront origin <br> - Perform end-to-end testing of the AI topology generation flow from the frontend | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |
|| 6   | - Integrate and verify the full feature workflow: AI generate topology, topology validation, simulation scan, simulation run, and simulation with defense <br> - Perform real-world testing from the CloudFront frontend interface to ensure stable operation across all features <br> - Fix the `simulation/with-defense` endpoint to return complete `attack_steps` and `defense_mechanisms` <br> - Optimize the Lambda function name and CloudFormation outputs | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |

### Week 12 Achievements:

* Backend fully deployed on AWS Lambda with FastAPI and executed through the Mangum adapter.
* API Gateway HTTP API is operational and exposes all endpoints for the frontend through CloudFront.
* Secrets Manager safely stores `GOOGLE_API_KEY`, and Lambda reads it through an IAM read grant.
* Frontend deployed to S3 and served through CloudFront CDN.
* CORS handled correctly via FastAPI CORSMiddleware, allowing requests from the CloudFront origin.
* Lambda Layer containing FastAPI, Mangum, and Google Generative AI ensures Lambda has all required dependencies.
* The full end-to-end flow from frontend to backend works stably: AI generate → topology validate → simulation scan → simulation run → simulation with defense.
* Infrastructure is fully managed through AWS CDK and can be redeployed at any time.
