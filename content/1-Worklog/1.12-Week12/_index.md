---
title: "Week 12 Worklog"
date: 2026-06-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* Deploy frontend to AWS (S3 + CloudFront).
* Complete frontend-backend integration and ensure CORS works properly.
* Integrate AI services (Gemini) and verify the entire feature flow.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Build `CloudNexus-Secrets` stack: create Secrets Manager to store `GOOGLE_API_KEY` <br> - Build `CloudNexus-Backend` stack: create Lambda function with FastAPI (ASGI via Mangum), API Gateway HTTP API, IAM roles <br> - Configure Lambda Layer with Python dependencies (`fastapi`, `mangum`, `google-genai`) <br> - First deployment of both stacks to AWS <br> - Initialize frontend structure: Vite + React + React Flow + Zustand + TailwindCSS <br> - Configure build script for frontend deployment to S3 bucket <br> - Deploy S3 bucket and set up CloudFront distribution for frontend | 06/06/2026 | 06/06/2026 | <https://docs.aws.amazon.com/cdk/api/v2/python/> <br> <https://docs.python.org/3/library/asyncio.html> <br> <https://github.com/jmaddock/lambda-pipeline> |
| 3 | - Fix CORS preflight (`OPTIONS`) request from CloudFront returning `400 Bad Request` from API Gateway <br> - Remove CORS config from API Gateway to avoid double-handling with FastAPI `CORSMiddleware` <br> - Add `@app.options` handler in FastAPI to handle preflight <br> - Update `allow_origins` in `CORSMiddleware` with CloudFront URL and localhost <br> - Add new Lambda Layer with full dependencies <br> - Rebuild and redeploy Lambda function | 07/06/2026 | 07/06/2026 | <https://vitejs.dev/guide/build> <br> <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Invalidation.html> |
| 4 | - Configure `VITE_API_URL` in `.env.production` pointing to API Gateway production endpoint <br> - Set up build configuration for Vite production mode <br> - Redeploy frontend bundle to S3, invalidate CloudFront cache <br> - Verify frontend connection from CloudFront URL to backend API | 08/06/2026 | 08/06/2026 | <https://fastapi.tiangolo.com/tutorial/first-steps/> <br> <https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS> |
| 5 | - Complete FastAPI backend: add `GET /` endpoint returning API metadata <br> - Verify all endpoints working correctly: `/api/health`, `/api/ai/generate`, `/api/topology/validate`, `/api/simulation/scan` <br> - Check CORS headers on all endpoints from CloudFront origin <br> - End-to-end test of AI generate topology flow from frontend | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |
| 6 | - Integrate and verify entire feature flow: AI generate topology, topology validation, simulation scan, simulation run, simulation with defense <br> - Practical test from frontend interface on CloudFront: all features working stably <br> - Fix `simulation/with-defense` endpoint to ensure full `attack_steps` and `defense_mechanisms` response <br> - Optimize Lambda function name and CloudFormation outputs | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |

### Week 12 Achievements:

* Backend fully deployed on AWS Lambda with FastAPI, running through Mangum adapter.
* API Gateway HTTP API is operational, exposing full endpoints for frontend via CloudFront.
* Secrets Manager stores `GOOGLE_API_KEY` securely; Lambda reads it via IAM grant read.
* Frontend deployed on S3 and served via CloudFront CDN.
* CORS properly handled via FastAPI `CORSMiddleware`, allowing requests from CloudFront origin.
* Lambda Layer containing `fastapi`, `mangum`, `google-genai` ensures Lambda has full dependencies.
* Entire flow from frontend to backend works stably: AI generate → topology validate → simulation scan → simulation run → simulation with defense.
* Infrastructure fully managed via AWS CDK, can be redeployed anytime.
