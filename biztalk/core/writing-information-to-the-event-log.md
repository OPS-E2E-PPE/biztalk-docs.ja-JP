---
title: イベント ログに情報を書き込む |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d7398dc-29d8-4a7a-bab4-c8f128b47dca
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae31f6c09e8ffaeb562aa5bd5380dd533173cad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261991"
---
# <a name="writing-information-to-the-event-log"></a><span data-ttu-id="72bf9-102">イベント ログに情報を書き込む</span><span class="sxs-lookup"><span data-stu-id="72bf9-102">Writing Information to the Event Log</span></span>
<span data-ttu-id="72bf9-103">既定のアプリケーション ログまたはカスタム イベント ログに情報を記述することで、BizTalk アプリケーション内のさまざまなビジネス プロセスの進行状況を監視することがあります。</span><span class="sxs-lookup"><span data-stu-id="72bf9-103">You may want to monitor the progress of the different business processes within your BizTalk application by writing information to the default Application log or to a custom event log.</span></span> <span data-ttu-id="72bf9-104">イベント ログへの書き込みは、次のシナリオで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="72bf9-104">Writing to the event log can be useful in the following scenarios:</span></span>  
  
-   <span data-ttu-id="72bf9-105">Windows によって提供されるツールを使用して標準的な方法でアプリケーション メッセージにアクセスするには。</span><span class="sxs-lookup"><span data-stu-id="72bf9-105">You want to access application messages in a standard way using tools supplied by Windows.</span></span>  
  
-   <span data-ttu-id="72bf9-106">完全な履歴用のサーバー環境から他のメッセージと情報をアーカイブするには。</span><span class="sxs-lookup"><span data-stu-id="72bf9-106">You want to archive information with other messages from the server environment for a more complete history.</span></span>  
  
-   <span data-ttu-id="72bf9-107">イベント ログと対話するためのツールを使用してアプリケーションを監視する機能を必要とします。</span><span class="sxs-lookup"><span data-stu-id="72bf9-107">You want the ability to monitor your application using tools that interact with the event log.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72bf9-108">System.Diagnostics.EventLog.WriteEntry メソッドには、メッセージ文字列のサイズ制限があります。</span><span class="sxs-lookup"><span data-stu-id="72bf9-108">The System.Diagnostics.EventLog.WriteEntry method has a size limitation on the message string.</span></span> <span data-ttu-id="72bf9-109">メッセージ文字列が 32,766 バイトを超える場合、例外を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="72bf9-109">You will receive exception if the message string exceeds 32766 bytes.</span></span>  
  
## <a name="writing-to-the-application-log"></a><span data-ttu-id="72bf9-110">アプリケーション ログへの書き込み</span><span class="sxs-lookup"><span data-stu-id="72bf9-110">Writing to the Application Log</span></span>  
 <span data-ttu-id="72bf9-111">使用して、コードからアプリケーション ログまたは他のログを記述することができます**System.Diagnostics.EventLog**次に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="72bf9-111">You can write to the Application log or any other log from your code by using **System.Diagnostics.EventLog** as shown in the following:</span></span>  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 <span data-ttu-id="72bf9-112">同様に、行うこともできます、</span><span class="sxs-lookup"><span data-stu-id="72bf9-112">Similar, you can also do,</span></span>  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 <span data-ttu-id="72bf9-113">使用する必要がある、カスタム ログを使用している場合、 **SourceExists**を記述する前にいることを確認するメソッドが存在します。</span><span class="sxs-lookup"><span data-stu-id="72bf9-113">If you are using a custom log, you should use the **SourceExists** method to ensure it exists before you write to it.</span></span>  
  
## <a name="writing-to-a-custom-log"></a><span data-ttu-id="72bf9-114">カスタム ログへの書き込み</span><span class="sxs-lookup"><span data-stu-id="72bf9-114">Writing to a Custom Log</span></span>  
 <span data-ttu-id="72bf9-115">カスタム ログへの書き込みは、カスタム ログを作成する必要がありますまず例外とアプリケーション ログへの書き込みに似ています。</span><span class="sxs-lookup"><span data-stu-id="72bf9-115">Writing to a custom log is similar to writing to the Application log with the exception that you must first create the custom log.</span></span> <span data-ttu-id="72bf9-116">カスタム ログを作成するコードは簡単です。</span><span class="sxs-lookup"><span data-stu-id="72bf9-116">The code to create a custom log is straightforward:</span></span>  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 <span data-ttu-id="72bf9-117">ただし、ことを想定しないでください、コードが新しいイベント ログを作成するセキュリティ特権を持つアカウントで実行されることです。</span><span class="sxs-lookup"><span data-stu-id="72bf9-117">However, you should not assume that your code will be run under an account that has the security privileges to create a new event log.</span></span> <span data-ttu-id="72bf9-118">イベント ログを作成して、管理者特権を受け取り、別のユーティリティ プログラムで、またはできれば .msi のインストールの一部として行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="72bf9-118">Creating an event log takes administrator privileges and should be done in a separate utility program or, ideally, as part of an .msi installation.</span></span> <span data-ttu-id="72bf9-119">エクスポートされた .msi のインストールでカスタム スクリプトの使用に関する詳細については、次を参照してください。[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="72bf9-119">For more information about using custom script with an exported .msi installation, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>