# Amazon Q Developer Prompt Flow

## How Amazon Q Developer Handles Your Prompts

When you use Amazon Q Developer in your IDE or through the CLI, here's what happens with your prompts:

1. **From Your IDE to AWS**: 
   - Your prompt and relevant code context are sent from your IDE to AWS through a secure API Gateway
   - The connection is authenticated using your AWS credentials

2. **Processing Your Request**:
   - A Lambda function processes your request
   - Your identity is verified through IAM
   - All requests are logged in CloudWatch for troubleshooting and service improvement
   - Your prompt and context may be temporarily stored in S3

3. **Generating Responses**:
   - Your prompt is sent to Amazon Bedrock (AWS's foundation model service)
   - Bedrock generates a response based on your prompt and context
   - The response is returned through the same secure channel

4. **Data Storage Policy**:
   - Your code is not permanently stored by Amazon Q
   - Context and prompts are only temporarily stored for processing
   - AWS maintains logs of interactions for service improvement and troubleshooting

## Visual Representation

A diagram showing this flow has been generated at: `/Users/kerrfir/generated-diagrams/amazon_q_prompt_flow.png.png`

## Privacy and Security

Amazon Q Developer is designed with privacy in mind:
- Your code is not used to train models
- Temporary storage follows AWS security best practices
- All communications are encrypted
- Access is controlled through your AWS credentials

For more detailed information about Amazon Q's data handling practices, refer to the [official AWS documentation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security.html).
