---
title: イベント ログに情報を書き込む |Microsoft ドキュメント
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
ms.openlocfilehash: f848cafd6ee9247511db3b9a6dad7dc5da91236b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289578"
---
# <a name="writing-information-to-the-event-log"></a><span data-ttu-id="328f3-102">イベント ログへの情報の書き込み</span><span class="sxs-lookup"><span data-stu-id="328f3-102">Writing Information to the Event Log</span></span>
<span data-ttu-id="328f3-103">既定のアプリケーション ログまたはカスタム イベント ログに情報を書き込むことで、BizTalk アプリケーション内の異なるビジネス プロセスの進捗を監視できます。</span><span class="sxs-lookup"><span data-stu-id="328f3-103">You may want to monitor the progress of the different business processes within your BizTalk application by writing information to the default Application log or to a custom event log.</span></span> <span data-ttu-id="328f3-104">イベント ログへの書き込みは、次のようなシナリオで役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="328f3-104">Writing to the event log can be useful in the following scenarios:</span></span>  
  
-   <span data-ttu-id="328f3-105">Windows で提供されているツールを使用し、標準的な方法でアプリケーションのメッセージにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="328f3-105">You want to access application messages in a standard way using tools supplied by Windows.</span></span>  
  
-   <span data-ttu-id="328f3-106">より完全な履歴を残すために、サーバー環境からの他のメッセージと共に情報をアーカイブする。</span><span class="sxs-lookup"><span data-stu-id="328f3-106">You want to archive information with other messages from the server environment for a more complete history.</span></span>  
  
-   <span data-ttu-id="328f3-107">イベント ログと対話できるツールを使用してアプリケーションを監視する。</span><span class="sxs-lookup"><span data-stu-id="328f3-107">You want the ability to monitor your application using tools that interact with the event log.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="328f3-108">System.Diagnostics.EventLog.WriteEntry メソッドには、メッセージ文字列に関してサイズ制限があります。</span><span class="sxs-lookup"><span data-stu-id="328f3-108">The System.Diagnostics.EventLog.WriteEntry method has a size limitation on the message string.</span></span> <span data-ttu-id="328f3-109">メッセージ文字列が 32,766 バイトを超えると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="328f3-109">You will receive exception if the message string exceeds 32766 bytes.</span></span>  
  
## <a name="writing-to-the-application-log"></a><span data-ttu-id="328f3-110">アプリケーション ログへの書き込み</span><span class="sxs-lookup"><span data-stu-id="328f3-110">Writing to the Application Log</span></span>  
 <span data-ttu-id="328f3-111">使用して、コードから、アプリケーション ログまたは他のログに記述することができます**System.Diagnostics.EventLog**次に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="328f3-111">You can write to the Application log or any other log from your code by using **System.Diagnostics.EventLog** as shown in the following:</span></span>  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 <span data-ttu-id="328f3-112">同様に、次のように記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="328f3-112">Similar, you can also do,</span></span>  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 <span data-ttu-id="328f3-113">使用する必要がある、カスタム ログを使用している場合、 **SourceExists**を記述する前にいることを確認するメソッドが存在します。</span><span class="sxs-lookup"><span data-stu-id="328f3-113">If you are using a custom log, you should use the **SourceExists** method to ensure it exists before you write to it.</span></span>  
  
## <a name="writing-to-a-custom-log"></a><span data-ttu-id="328f3-114">カスタム ログへの書き込み</span><span class="sxs-lookup"><span data-stu-id="328f3-114">Writing to a Custom Log</span></span>  
 <span data-ttu-id="328f3-115">カスタム ログへの書き込みはアプリケーション ログへの書き込みと似ていますが、最初にカスタム ログを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="328f3-115">Writing to a custom log is similar to writing to the Application log with the exception that you must first create the custom log.</span></span> <span data-ttu-id="328f3-116">カスタム ログは簡単なコードで作成できます。</span><span class="sxs-lookup"><span data-stu-id="328f3-116">The code to create a custom log is straightforward:</span></span>  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 <span data-ttu-id="328f3-117">ただし、新しいイベント ログを作成するためのセキュリティ特権を持つアカウントでコードが実行されることを前提にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="328f3-117">However, you should not assume that your code will be run under an account that has the security privileges to create a new event log.</span></span> <span data-ttu-id="328f3-118">イベント ログの作成には管理者特権が必要であり、別のユーティリティ プログラムで、またはできれば .msi インストールの一部として作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="328f3-118">Creating an event log takes administrator privileges and should be done in a separate utility program or, ideally, as part of an .msi installation.</span></span> <span data-ttu-id="328f3-119">エクスポートされた .msi のインストールでカスタム スクリプトを使用する方法の詳細については、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="328f3-119">For more information about using custom script with an exported .msi installation, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>