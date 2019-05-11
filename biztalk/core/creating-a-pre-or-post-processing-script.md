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
ms.openlocfilehash: f20c95273cc0140da79ac1972be2071f40e0c348
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354105"
---
# <a name="creating-a-pre--or-post-processing-script"></a>処理前または処理後のスクリプトの作成
アプリケーションの展開時に操作を実行するスクリプトを作成し、展開プロセスのどの時点でそのスクリプトを実行するかを定義できます。 同じスクリプトにインストールとクリーンアップ コードの両方を含めることができます。これらのコードは環境変数を使って区切ります。 コマンドライン引数をスクリプトに渡すこともできます。  
  
> [!CAUTION]
>  スクリプトを記述する場合は、常にサイレント モードの運用システムを想定してください。 スクリプトでユーザーからの入力を待機すると、その間 BizTalk データベースがロックされ、入力を受け取るまでアクセスできなくなります。  
  
## <a name="specifying-when-a-script-will-run-during-deployment"></a>展開時にスクリプトを実行するタイミングを指定する  
 スクリプトをアプリケーションに追加するときに、スクリプトを System.BizTalk:PreProcessingScript (処理前のスクリプト) または System.BizTalk:PostProcessingScript (処理後のスクリプト) に追加して、スクリプトを実行するタイミングを指定します。  
  
 処理前および処理後のスクリプトは次のように実行されます。  
  
- 処理前のスクリプトは、インポートまたはインストール プロセスの最初に実行されます。  
  
- 処理後のスクリプトは、インポートまたはインストール プロセスの最後に実行されます。  
  
- アンインストール時、すべてのスクリプトはインストール時と逆の順番で実行されます。 つまり、処理後のスクリプトがアンインストールの最初に実行され、処理前のスクリプトがアンインストールの最後に実行されます。  
  
- インストールに失敗した場合、スクリプトは適切なロールバック アクションと共に逆の順番で呼び出されます。  
  
  前または処理後のスクリプトを呼び出されると、展開の状態を決定します (インストール、インポート、削除、アンインストール、インポート ロールバック、またはインストール ロールバック) ことにより、実行中環境変数 BTAD_ChangeRequestAction、BTAD_InstallMode、および BTAD_HostClass、」の説明に従って[方法環境変数を示す配置状態](../core/how-environment-variables-indicate-deployment-state.md)します。 変数に関するリファレンス情報は、次を参照してください。[前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md)します。  
  
  スクリプト アプリケーションを追加する方法の詳細については、次を参照してください。[より前に追加する方法または処理後のスクリプトをアプリケーションに](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)します。  
  
> [!NOTE]
>  コマンドライン引数をスクリプトに含めるには、AddResource コマンドを使用してスクリプトを追加する必要があります。後の説明を参照してください。  
  
## <a name="supported-script-file-extensions"></a>サポートされるスクリプト ファイルの拡張子  
 次のスクリプト ファイルの拡張機能がサポートされています: .com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf、および .wsh です。 この拡張子のセットは、PATHEXT 環境変数で定義されています。  
  
## <a name="logging-errors"></a>エラーのログ記録  
 ベスト プラクティスとして、スクリプトごとにエラーをログ ファイルに記録するよう構成することをお勧めします。 この理由は、Windows インストーラーではスクリプトで発生したエラーが記録されないためです。 スクリプトを実行した後はこれらのログを確認し、対処が必要なエラーがないかどうかを確認してください。  
  
 エラーが発生した時点を確認できるよう、ログ ファイルに日時を含めることができます。  
  
 ログ ファイルを指定し、エラーを記録するには、次のコードを使用します。  
  
 `Set LogFile=<full path of log file>`  
  
 `…`  
  
 `echo %DATE% %TIME% <text> >> %LogFile%`  
  
 次の例では、公開キー トークンが定義されていない場合、指定したログ ファイルにエントリが作成されます。 ログ ファイル内では、"Public key should be set in script." というテキストと同じ行に日時が記録されます。  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 行 `exit /b 1` をスクリプトに追加して Windows インストーラー用のエラー コードを生成することもできます。これにより、ロール バックが実行されるようになります。  
  
 次の例では、公開キー トークンが定義されていない場合、スクリプトは Windows インストーラーにエラーを返し、インストーラーではロール バックが実行されます。  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 `exit /b 1`  
  
## <a name="including-installation-and-cleanup-code-in-the-same-script"></a>同じスクリプトにインストールとクリーンアップ コードを含める  
 インストール時とアンインストール時では、逆の順番でスクリプトが実行されるため、インストールとクリーンアップ コードを同じスクリプトの条件ステートメント内に含めることができます。 たとえば、インストール コードは次のようにインストール モードを確認する条件ステートメント内に配置できます。  
  
```  
  
%BTAD_ChangeRequestAction%=Update AND %BTAD_InstallMode%=Install  
  
```  
  
 クリーンアップ コードは次のようにインストール モードを確認する条件ステートメント内で限定できます。  
  
```  
  
%BTAD_ChangeRequestAction%=Delete AND %BTAD_InstallMode%=Uninstall  
  
```  
  
## <a name="passing-in-command-line-arguments"></a>コマンド ライン引数を渡す  
 BTSTask AddResource コマンドを使用してスクリプトをアプリケーションに追加するときには、次のパラメーターを指定してスクリプトにコマンド ライン引数を渡すことができます。 この場合、引数はスクリプトが呼び出された時にスクリプトに渡されます。  
  
 **/Property:Args =**"*引数リスト*"  
  
> [!NOTE]
>  アプリケーションに処理前および処理後のスクリプトが複数ある場合、スクリプトは特に順序に関係なく実行されます。  
  
> [!IMPORTANT]
>  BTSTask コマンドはスクリプトで使用しないでください。特にインポート時に実行されるスクリプトでは使用しないでください。スクリプトはインポートと同じトランザクションに参加しません。  
  
 AddResource コマンドを使用して、アプリケーションにスクリプトを追加する手順については、次を参照してください。 [AddResource コマンド。スクリプトを前処理](../core/addresource-command-preprocessing-script.md)します。 参照してください[AddResource コマンド。処理後のスクリプト](../core/addresource-command-postprocessing-script.md)  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [Template (アプリケーションの展開サンプル)](../core/template-application-deployment-sample.md)