# screenshot-to-code

This simple app converts a screenshot to code (HTML/Tailwind CSS, or React or Bootstrap or Vue). It uses GPT-4 Vision to generate the code and DALL-E 3 to generate similar-looking images. You can now also enter a URL to clone a live website!

https://github.com/abi/screenshot-to-code/assets/23818/6cebadae-2fe3-4986-ac6a-8fb9db030045

See the [Examples](#-examples) section below for more demos.

## 🚀 Try It Out!

🆕 [Try it here](https://screenshottocode.com) (bring your own OpenAI key - **your key must have access to GPT-4 Vision. See [FAQ](#%EF%B8%8F-faqs) section below for details**). Or see [Getting Started](#-getting-started) below for local install instructions.

## 🌟 Recent Updates

- Dec 11 - Start a new project from existing code (allows you to come back to an older project)
- Dec 7 - 🔥 🔥 🔥 View a history of your edits, and branch off them
- Nov 30 - Dark mode, output code in Ionic (thanks [@dialmedu](https://github.com/dialmedu)), set OpenAI base URL
- Nov 28 - 🔥 🔥 🔥 Customize your stack: React or Bootstrap or TailwindCSS
- Nov 23 - Send in a screenshot of the current replicated version (sometimes improves quality of subsequent generations)
- Nov 21 - Edit code in the code editor and preview changes live thanks to [@clean99](https://github.com/clean99)
- Nov 20 - Paste in a URL to screenshot and clone (requires [ScreenshotOne free API key](https://screenshotone.com?via=screenshot-to-code))
- Nov 19 - Support for dark/light code editor theme - thanks [@kachbit](https://github.com/kachbit)
- Nov 16 - Added a setting to disable DALL-E image generation if you don't need that
- Nov 16 - View code directly within the app
- Nov 15 - You can now instruct the AI to update the code as you wish. It is helpful if the AI messed up some styles or missed a section.

## 🛠 Getting Started

The app has a React/Vite frontend and a FastAPI backend. You will need an OpenAI API key with access to the GPT-4 Vision API.

Run the backend (I use Poetry for package management - `pip install poetry` if you don't have it):

```bash
cd backend
echo "OPENAI_API_KEY=sk-your-key" > .env
poetry install
poetry shell
poetry run uvicorn main:app --reload --port 7001
```

You can also run the backend (when you're in `backend`):

```bash
poetry run pyright
```

Run the frontend:

```bash
cd frontend
yarn
yarn dev
```

Open http://localhost:5173 to use the app.

If you prefer to run the backend on a different port, update VITE_WS_BACKEND_URL in `frontend/.env.local`

For debugging purposes, if you don't want to waste GPT4-Vision credits, you can run the backend in mock mode (which streams a pre-recorded response):

```bash
MOCK=true poetry run uvicorn main:app --reload --port 7001
```

## Configuration

- You can configure the OpenAI base URL if you need to use a proxy: Set OPENAI_BASE_URL in the `backend/.env` or directly in the UI in the settings dialog

## Docker

If you have Docker installed on your system, in the root directory, run:

```bash
echo "OPENAI_API_KEY=sk-your-key" > .env
docker-compose up -d --build
```

The app will be up and running at http://localhost:5173. Note that you can't develop the application with this setup as the file changes won't trigger a rebuild.

## 🙋‍♂️ FAQs

- **I'm running into an error when setting up the backend. How can I fix it?** [Try this](https://github.com/abi/screenshot-to-code/issues/3#issuecomment-1814777959). If that still doesn't work, open an issue.
- **How do I get an OpenAI API key?** See https://github.com/abi/screenshot-to-code/blob/main/Troubleshooting.md
- **How can I provide feedback?** For feedback, feature requests and bug reports, open an issue or ping me on [Twitter](https://twitter.com/_abi_).

## 📚 Examples

**NYTimes**

| Original                                                                                                                                                        | Replica                                                                                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <img width="1238" alt="Screenshot 2023-11-20 at 12 54 03 PM" src="https://github.com/abi/screenshot-to-code/assets/23818/3b644dfa-9ca6-4148-84a7-3405b6671922"> | <img width="1414" alt="Screenshot 2023-11-20 at 12 59 56 PM" src="https://github.com/abi/screenshot-to-code/assets/23818/26201c9f-1a28-4f35-a3b1-1f04e2b8ce2a"> |

**Instagram page (with not Taylor Swift pics)**

https://github.com/abi/screenshot-to-code/assets/23818/503eb86a-356e-4dfc-926a-dabdb1ac7ba1

**Hacker News** but it gets the colors wrong at first so we nudge it

https://github.com/abi/screenshot-to-code/assets/23818/3fec0f77-44e8-4fb3-a769-ac7410315e5d

## 🌍 Hosted Version

🆕 [Try it here](https://screenshottocode.com) (bring your own OpenAI key - **your key must have access to GPT-4 Vision. See [FAQ](#%EF%B8%8F-faqs) section for details**). Or see [Getting Started](#-getting-started) for local install instructions.

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/abiraja)


# **screenshot-to-code**

项目地址， https://github.com/abi/screenshot-to-code

如果你没有安装过Python或者Yarn，那就用下面两条命令来安装Python，Node或者Yarn

```jsx
brew install python
brew install node
brew install yarn
brew install git
```

并且通过一下两个命令来确认，安装是否成功

```jsx
node --version
npm --version
python --version
yarn --version

Node: v18.12.1
npm: 8.19.2
Python: 3.11.5
Yarn: 1.22.19
```

这个软件对版本要求并不高，所以最新版的就行，我用的版本如下，你可以对照一下

然后Clone这个软件包

```jsx
git clone https://github.com/abi/screenshot-to-code
# 进入软件目录
cd screenshot-to-code
# 进入后台目录
cd backend
# GPT4 的API key
echo "OPENAI_API_KEY=sk-your-key" > .env
# 安装Poetry 依赖包管理器
pip install poetry
# 安装依赖包
poetry install
# 激活命令行
poetry shell
# 运行程序
poetry run uvicorn main:app --reload --port 7000
```

后台运行好之后，再打开另外一个命令行

来运行前段程序

```jsx
# 同样的进入软件目录
cd screenshot-to-code
# 进入前台目录
cd frontend
# 安装前台依赖包
yarn
yarn dev
```

打开浏览器地址，就可以使用了

http://localhost:5173/
