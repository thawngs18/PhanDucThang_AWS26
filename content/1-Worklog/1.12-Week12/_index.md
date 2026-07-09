---
title: "Week 12 Worklog"
date: 2026-06-13
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* Deploy frontend to AWS using S3 and CloudFront.
* Complete frontend-backend integration and ensure CORS works end to end.
* Integrate AI services and verify the full application workflow.

### Tasks to be carried out this week:

|| Day | Task | Start Date | Completion Date | Reference Material |
|| --- | ---- | ---------- | --------------- | ------------------ |
|| 2   | - Build `CloudNexus-Secrets` stack and create Secrets Manager to store `GOOGLE_API_KEY` <br> - Build `CloudNexus-Backend` stack with Lambda using FastAPI via Mangum, API Gateway HTTP API, and IAM roles <br> - Configure Lambda Layer for Python dependencies: `fastapi`, `mangum`, and `google-genai` <br> - Deploy both stacks to AWS for the first time <br> - Initialize frontend structure with Vite + React + React Flow + Zustand + TailwindCSS <br> - Configure build script for deploying frontend to an S3 bucket <br> - Deploy S3 bucket and set up CloudFront distribution to serve the frontend | 06/06/2026 | 06/06/2026 | <https://docs.aws.amazon.com/cdk/api/v2/python/> <br> <https://docs.python.org/3/library/asyncio.html> <br> <https://github.com/jmaddock/lambda-pipeline> |
|| 3   | - Fix CORS preflight `OPTIONS` requests failing from CloudFront through API Gateway with `400 Bad Request` <br> - Remove API Gateway CORS config to avoid double handling with FastAPI CORSMiddleware <br> - Add `@app.options` handler in FastAPI to handle preflight requests <br> - Update `allow_origins` in CORSMiddleware to include CloudFront URL and localhost <br> - Add a new Lambda Layer with complete dependencies <br> - Rebuild and redeploy the Lambda function | 07/06/2026 | 07/06/2026 | <https://vitejs.dev/guide/build> <br> <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html> |
|| 4   | - Configure `VITE_API_URL` in `.env.production` to point to the production API Gateway endpoint <br> - Set up Vite build configuration for production mode <br> - Redeploy the built frontend bundle to S3 and invalidate CloudFront cache <br> - Verify frontend connectivity from CloudFront to backend API | 08/06/2026 | 08/06/2026 | <https://fastapi.tiangolo.com/tutorial/first-steps/> <br> <https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS> |
|| 5   | - Complete FastAPI backend by adding `GET /` endpoint returning API metadata <br> - Verify all endpoints: `/api/health`, `/api/ai/generate`, `/api/topology/validate`, and `/api/simulation/scan` <br> - Check CORS headers on all endpoints from CloudFront origin <br> - End-to-end test the AI topology generation flow from the frontend | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |
|| 6   | - Integrate and verify the full workflow: AI generate topology, topology validation, simulation scan, simulation run, and simulation with defense <br> - Perform real tests from the CloudFront-hosted frontend to ensure all features are stable <br> - Fix `/api/simulation/with-defense` to return complete `attack_steps` and `defense_mechanisms` <br> - Optimize Lambda function naming and CloudFormation outputs | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |

### Week 12 Achievements:

* Backend is fully deployed on AWS Lambda with FastAPI and runs through the Mangum adapter.
* API Gateway HTTP API is live and exposes complete endpoints for the CloudFront frontend.
* Secrets Manager securely stores `GOOGLE_API_KEY`, and Lambda reads it through IAM grant.
* Frontend is deployed to S3 and served through CloudFront CDN.
* CORS is correctly handled via FastAPI CORSMiddleware, allowing requests from the CloudFront origin.
* Lambda Layer contains `fastapi`, `mangum`, and `google-genai`, ensuring Lambda has full dependencies.
* The complete end-to-end flow from frontend to backend works stably: AI generate topology, topology validation, simulation scan, simulation run, and simulation with defense.
* Infrastructure is managed entirely through AWS CDK and can be redeployed at any time.
