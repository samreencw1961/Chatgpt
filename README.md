# Chatgpt

# Create a new project with the default template
npx assistant-ui@latest create



#for API using gemini api
#in terminal,run the command.
npm install ai @assistant-ui/react-ai-sdk @ai-sdk/google

create .env
import { google } from "@ai-sdk/google";
import { streamText } from "ai";

export const maxDuration = 30;

export async function POST(req: Request) {
  const { messages } = await req.json();
  const result = streamText({
    model: google("gemini-2.0-flash"),
    messages,
  });
  return result.toDataStreamResponse();
}

create .env.local
GOOGLE_GENERATIVE_AI_API_KEY="xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
