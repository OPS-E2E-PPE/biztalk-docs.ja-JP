---
title: 前に作成または処理後のスクリプト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, post-processing
- scripts, pre-processing
- scripts, warnings
- scripts, applications
- applications, scripts
- scripts, deploying
- deploying, scripts
ms.assetid: d5fbaec8-fbfe-4ceb-8ba8-0933baa37a1f
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6993ab2786cc33e40f00bab7910353170e318db0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006475"
---
# <a name="creating-a-pre--or-post-processing-script"></a><span data-ttu-id="31847-102">処理前または処理後のスクリプトの作成</span><span class="sxs-lookup"><span data-stu-id="31847-102">Creating a Pre- or Post-processing Script</span></span>
<span data-ttu-id="31847-103">アプリケーションの展開時に操作を実行するスクリプトを作成し、展開プロセスのどの時点でそのスクリプトを実行するかを定義できます。</span><span class="sxs-lookup"><span data-stu-id="31847-103">You can create a script to perform actions when an application is deployed, and then define when it will run during the deployment process.</span></span> <span data-ttu-id="31847-104">同じスクリプトにインストールとクリーンアップ コードの両方を含めることができます。これらのコードは環境変数を使って区切ります。</span><span class="sxs-lookup"><span data-stu-id="31847-104">You can include both installation and cleanup code in the same script, using environment variables to delimit the code.</span></span> <span data-ttu-id="31847-105">コマンドライン引数をスクリプトに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="31847-105">You can also pass command-line arguments into the script.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="31847-106">スクリプトを記述する場合は、常にサイレント モードの運用システムを想定してください。</span><span class="sxs-lookup"><span data-stu-id="31847-106">You should always write scripts intended for production systems in silent mode.</span></span> <span data-ttu-id="31847-107">スクリプトでユーザーからの入力を待機すると、その間 BizTalk データベースがロックされ、入力を受け取るまでアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="31847-107">This is because a script waiting for user input will cause the BizTalk databases to become locked and inaccessible until the input is received.</span></span>  
  
## <a name="specifying-when-a-script-will-run-during-deployment"></a><span data-ttu-id="31847-108">展開時にスクリプトを実行するタイミングを指定する</span><span class="sxs-lookup"><span data-stu-id="31847-108">Specifying when a script will run during deployment</span></span>  
 <span data-ttu-id="31847-109">スクリプトをアプリケーションに追加するときに、スクリプトを System.BizTalk:PreProcessingScript (処理前のスクリプト) または System.BizTalk:PostProcessingScript (処理後のスクリプト) に追加して、スクリプトを実行するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="31847-109">You specify when a script will run when you add the script to an application by adding it as either a System.BizTalk:PreProcessingScript (pre-processing script) or a System.BizTalk:PostProcessingScript (post-processing script).</span></span>  
  
 <span data-ttu-id="31847-110">処理前および処理後のスクリプトは次のように実行されます。</span><span class="sxs-lookup"><span data-stu-id="31847-110">Pre- and post-processing scripts run as follows:</span></span>  
  
- <span data-ttu-id="31847-111">処理前のスクリプトは、インポートまたはインストール プロセスの最初に実行されます。</span><span class="sxs-lookup"><span data-stu-id="31847-111">Pre-processing scripts run at the beginning of the import or installation process.</span></span>  
  
- <span data-ttu-id="31847-112">処理後のスクリプトは、インポートまたはインストール プロセスの最後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="31847-112">Post-processing scripts run at the end of the import or installation process.</span></span>  
  
- <span data-ttu-id="31847-113">アンインストール時、すべてのスクリプトはインストール時と逆の順番で実行されます。</span><span class="sxs-lookup"><span data-stu-id="31847-113">During uninstallation, all scripts run in the opposite order that they run during installation.</span></span> <span data-ttu-id="31847-114">つまり、処理後のスクリプトがアンインストールの最初に実行され、処理前のスクリプトがアンインストールの最後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="31847-114">Therefore, post-processing scripts run at the beginning of uninstallation and pre-processing scripts at the end of uninstallation.</span></span>  
  
- <span data-ttu-id="31847-115">インストールに失敗した場合、スクリプトは適切なロールバック アクションと共に逆の順番で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="31847-115">If an installation fails, scripts are called in reverse order with the appropriate rollback action.</span></span>  
  
  <span data-ttu-id="31847-116">前または処理後のスクリプトを呼び出されると、展開の状態を決定します (インストール、インポート、削除、アンインストール、インポート ロールバック、またはインストール ロールバック) ことにより、実行中環境変数 BTAD_ChangeRequestAction、BTAD_InstallMode、および BTAD_HostClass、」の説明に従って[方法環境変数を示す配置状態](../core/how-environment-variables-indicate-deployment-state.md)します。</span><span class="sxs-lookup"><span data-stu-id="31847-116">Once invoked, a pre- or post-processing script determines which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running in by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode, and BTAD_HostClass, as described in [How Environment Variables Indicate Deployment State](../core/how-environment-variables-indicate-deployment-state.md).</span></span> <span data-ttu-id="31847-117">変数に関するリファレンス情報は、[前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31847-117">For reference information about the variables, see [Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md).</span></span>  
  
  <span data-ttu-id="31847-118">スクリプト アプリケーションを追加する方法の詳細については、[より前に追加する方法または処理後のスクリプトをアプリケーションに](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31847-118">For instructions on adding a script to an application, see [How to Add a Pre- or Post-processing Script to an Application](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31847-119">コマンドライン引数をスクリプトに含めるには、AddResource コマンドを使用してスクリプトを追加する必要があります。後の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31847-119">If you want to include command-line arguments in a script, as discussed later in this topic, you must use the AddResource command to add the script.</span></span>  
  
## <a name="supported-script-file-extensions"></a><span data-ttu-id="31847-120">サポートされるスクリプト ファイルの拡張子</span><span class="sxs-lookup"><span data-stu-id="31847-120">Supported script file extensions</span></span>  
 <span data-ttu-id="31847-121">次のスクリプト ファイルの拡張機能がサポートされています: .com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf、および .wsh です。</span><span class="sxs-lookup"><span data-stu-id="31847-121">The following script file extensions are supported: .com, .exe, .bat, .cmd, .vbs, .vbe, .js, .jse, .wsf, and .wsh.</span></span> <span data-ttu-id="31847-122">この拡張子のセットは、PATHEXT 環境変数で定義されています。</span><span class="sxs-lookup"><span data-stu-id="31847-122">This set of extensions is defined in the PATHEXT environment variable.</span></span>  
  
## <a name="logging-errors"></a><span data-ttu-id="31847-123">エラーのログ記録</span><span class="sxs-lookup"><span data-stu-id="31847-123">Logging errors</span></span>  
 <span data-ttu-id="31847-124">ベスト プラクティスとして、スクリプトごとにエラーをログ ファイルに記録するよう構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31847-124">As a best practice, you should configure each script to log errors to a file.</span></span> <span data-ttu-id="31847-125">この理由は、Windows インストーラーではスクリプトで発生したエラーが記録されないためです。</span><span class="sxs-lookup"><span data-stu-id="31847-125">This is because Windows Installer does not log errors generated in the scripts.</span></span> <span data-ttu-id="31847-126">スクリプトを実行した後はこれらのログを確認し、対処が必要なエラーがないかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="31847-126">You should check these logs after the script runs for any errors that need to be addressed.</span></span>  
  
 <span data-ttu-id="31847-127">エラーが発生した時点を確認できるよう、ログ ファイルに日時を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="31847-127">To help you determine when the error occurred, you can include the date and time in the log file.</span></span>  
  
 <span data-ttu-id="31847-128">ログ ファイルを指定し、エラーを記録するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="31847-128">Use the following code to specify a log file and then log an error to it.</span></span>  
  
 `Set LogFile=<full path of log file>`  
  
 `…`  
  
 `echo %DATE% %TIME% <text> >> %LogFile%`  
  
 <span data-ttu-id="31847-129">次の例では、公開キー トークンが定義されていない場合、指定したログ ファイルにエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="31847-129">In the following example, when the public key token is not defined, an entry is made in the specified log file.</span></span> <span data-ttu-id="31847-130">ログ ファイル内では、"Public key should be set in script." というテキストと同じ行に日時が記録されます。</span><span class="sxs-lookup"><span data-stu-id="31847-130">In the log file, the date and time is written in the same line as the text, "Public key should be set in script."</span></span>  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 <span data-ttu-id="31847-131">行 `exit /b 1` をスクリプトに追加して Windows インストーラー用のエラー コードを生成することもできます。これにより、ロール バックが実行されるようになります。</span><span class="sxs-lookup"><span data-stu-id="31847-131">You can also add the line `exit /b 1` to a script to generate an error code for Windows Installer, which will cause it to roll back.</span></span>  
  
 <span data-ttu-id="31847-132">次の例では、公開キー トークンが定義されていない場合、スクリプトは Windows インストーラーにエラーを返し、インストーラーではロール バックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="31847-132">In the following example, if the public key token has not been defined, the script will return an error to Windows Installer, and the installer will roll back.</span></span>  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 `exit /b 1`  
  
## <a name="including-installation-and-cleanup-code-in-the-same-script"></a><span data-ttu-id="31847-133">同じスクリプトにインストールとクリーンアップ コードを含める</span><span class="sxs-lookup"><span data-stu-id="31847-133">Including installation and cleanup code in the same script</span></span>  
 <span data-ttu-id="31847-134">インストール時とアンインストール時では、逆の順番でスクリプトが実行されるため、インストールとクリーンアップ コードを同じスクリプトの条件ステートメント内に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="31847-134">Because scripts run in the opposite order during installation and uninstallation, you can include installation and cleanup code in the same script, inside a conditional statement.</span></span> <span data-ttu-id="31847-135">たとえば、インストール コードは次のようにインストール モードを確認する条件ステートメント内に配置できます。</span><span class="sxs-lookup"><span data-stu-id="31847-135">For example, you can place the installation code within a conditional statement that checks for the installation mode, as follows:</span></span>  
  
```  
  
%BTAD_ChangeRequestAction%=Update AND %BTAD_InstallMode%=Install  
  
```  
  
 <span data-ttu-id="31847-136">クリーンアップ コードは次のようにインストール モードを確認する条件ステートメント内で限定できます。</span><span class="sxs-lookup"><span data-stu-id="31847-136">You can qualify cleanup code within a conditional statement that checks for the installation mode, as follows:</span></span>  
  
```  
  
%BTAD_ChangeRequestAction%=Delete AND %BTAD_InstallMode%=Uninstall  
  
```  
  
## <a name="passing-in-command-line-arguments"></a><span data-ttu-id="31847-137">コマンド ライン引数を渡す</span><span class="sxs-lookup"><span data-stu-id="31847-137">Passing in command-line arguments</span></span>  
 <span data-ttu-id="31847-138">BTSTask AddResource コマンドを使用してスクリプトをアプリケーションに追加するときには、次のパラメーターを指定してスクリプトにコマンド ライン引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="31847-138">You can pass command-line arguments into the script by specifying the following parameter when you use the BTSTask AddResource command to add the script to the application.</span></span> <span data-ttu-id="31847-139">この場合、引数はスクリプトが呼び出された時にスクリプトに渡されます。</span><span class="sxs-lookup"><span data-stu-id="31847-139">When you do this, the arguments are passed to the script when the script is invoked.</span></span>  
  
 <span data-ttu-id="31847-140">**/Property:Args =**"*引数リスト*"</span><span class="sxs-lookup"><span data-stu-id="31847-140">**/Property:Args=**"*argument list*"</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31847-141">アプリケーションに処理前および処理後のスクリプトが複数ある場合、スクリプトは特に順序に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="31847-141">If you have multiple pre- or post-processing scripts in and application, they are run in no particular order.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="31847-142">BTSTask コマンドはスクリプトで使用しないでください。特にインポート時に実行されるスクリプトでは使用しないでください。スクリプトはインポートと同じトランザクションに参加しません。</span><span class="sxs-lookup"><span data-stu-id="31847-142">You should not use BTSTask commands in scripts, especially those that run during import, because scripts are not enlisted in the same transaction as an import.</span></span>  
  
 <span data-ttu-id="31847-143">AddResource コマンドを使用して、アプリケーションにスクリプトを追加する手順については、[AddResource コマンド: 前処理スクリプト](../core/addresource-command-preprocessing-script.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31847-143">For instructions on using the AddResource command to add a script to an application, see [AddResource Command: Preprocessing Script](../core/addresource-command-preprocessing-script.md).</span></span> <span data-ttu-id="31847-144">参照してください[AddResource コマンド: 処理後のスクリプト](../core/addresource-command-postprocessing-script.md)</span><span class="sxs-lookup"><span data-stu-id="31847-144">Also see [AddResource Command: Postprocessing Script](../core/addresource-command-postprocessing-script.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31847-145">参照</span><span class="sxs-lookup"><span data-stu-id="31847-145">See Also</span></span>  
 <span data-ttu-id="31847-146">[前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="31847-146">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 [<span data-ttu-id="31847-147">Template (アプリケーションの展開サンプル)</span><span class="sxs-lookup"><span data-stu-id="31847-147">Template (Application Deployment Sample)</span></span>](../core/template-application-deployment-sample.md)