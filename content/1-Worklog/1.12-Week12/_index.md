---
title: "Week 12 Worklog"
date: 2026-06-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* Deploy frontend to AWS using S3 and CloudFront.
* Complete frontend-backend integration with working CORS configuration.
* Integrate AI services and verify end-to-end feature flow.

### Tasks to be carried out this week:

|| Day | Task | Start Date | Completion Date | Reference Material |
|| --- | ---- | ---------- | --------------- | ------------------ |
|| 2   | - Build `CloudNexus-Secrets` stack: create Secrets Manager to store `GOOGLE_API_KEY` <br> - Build `CloudNexus-Backend` stack: create Lambda function with FastAPI via Mangum, API Gateway HTTP API, and IAM roles <br> - Configure Lambda Layer with Python dependencies (`fastapi`, `mangum`, `google-genai`) <br> - Perform initial deployment for both stacks to AWS <br> - Initialize frontend structure with Vite + React + React Flow + Zustand + TailwindCSS <br> - Configure build script for frontend deployment to S3 bucket <br> - Deploy S3 bucket and set up CloudFront distribution for frontend hosting | 06/06/2026 | 06/06/2026 | <https://docs.aws.amazon.com/cdk/api/v2/python/> |
|| 3   | - Fix CORS preflight `OPTIONS` requests returning `400 Bad Request` from API Gateway through CloudFront <br> - Remove API Gateway CORS config to avoid double-handling with FastAPI `CORSMiddleware` <br> - Add `@app.options` handler in FastAPI to handle preflight requests <br> - Update `allow_origins` in `CORSMiddleware` with CloudFront URL and localhost <br> - Add new Lambda Layer with complete dependencies <br> - Rebuild and redeploy Lambda function | 07/06/2026 | 07/06/2026 | <https://vitejs.dev/guide/build> |
|| 4   | - Configure `VITE_API_URL` in `.env.production` to point to production API Gateway endpoint <br> - Set up Vite production build configuration <br> - Redeploy frontend bundle to S3 and invalidate CloudFront cache <br> - Verify frontend connection from CloudFront URL to backend API | 08/06/2026 | 08/06/2026 | <https://fastapi.tiangolo.com/tutorial/first-steps/> |
|| 5   | - Complete FastAPI backend: add `GET /` endpoint returning API metadata <br> - Verify all endpoints: `/api/health`, `/api/ai/generate`, `/api/topology/validate`, `/api/simulation/scan` <br> - Check CORS headers on all endpoints from CloudFront origin <br> - Test end-to-end AI generate topology flow from frontend | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |
|| 6   | - Integrate and verify full feature flow: AI generate topology, topology validation, simulation scan, simulation run, and simulation with defense <br> - Perform real-world testing from CloudFront frontend UI to ensure stable operation of all features <br> - Fix `simulation/with-defense` endpoint to return complete `attack_steps` and `defense_mechanisms` <br> - Optimize Lambda function naming and CloudFormation outputs | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/lambda/latest/dg/nodejs-package.html> |

### Week 12 Achievements:

* Backend fully deployed on AWS Lambda with FastAPI through Mangum adapter.
* API Gateway HTTP API operational and exposing all endpoints for frontend access via CloudFront.
* Secrets Manager securely stores `GOOGLE_API_KEY`, with Lambda reading it through IAM read permissions.
* Frontend deployed to S3 and served via CloudFront CDN.
* CORS handled correctly through FastAPI `CORSMiddleware`, allowing requests from the CloudFront origin.
* Lambda Layer containing `fastapi`, `mangum`, and `google-genai` ensures complete Lambda dependencies.
* Full end-to-end flow from frontend to backend runs stably: AI generate → topology validate → simulation scan → simulation run → simulation with defense.
* Infrastructure is fully managed via AWS CDK and can be redeployed at any time.
