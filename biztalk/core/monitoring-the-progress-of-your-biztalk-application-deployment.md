---
title: "BizTalk アプリケーションの展開の進行状況の監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring, deploying
- applications, monitoring
- deploying [applications], monitoring
- monitoring, applications
ms.assetid: a69a8288-0203-440f-9805-52786525e193
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eaa81067f5a413c689a4a51ac6b102d80782e2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a><span data-ttu-id="18375-102">BizTalk アプリケーション展開の進行状況の監視</span><span class="sxs-lookup"><span data-stu-id="18375-102">Monitoring the Progress of Your BizTalk Application Deployment</span></span>
<span data-ttu-id="18375-103">BizTalk アプリケーションの展開の進行状況は、2 つの方法で監視できます。</span><span class="sxs-lookup"><span data-stu-id="18375-103">You can monitor the progress of your BizTalk application deployment in two ways:</span></span>  
  
-   <span data-ttu-id="18375-104">**BizTalk インストール ログ**: インストールを参照してくださいをログに記録[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="18375-104">**BizTalk installation log**: You can consult the installation log that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates.</span></span> <span data-ttu-id="18375-105">インストール ログに %SystemDrive%\Documents and Settings\\<*現在のユーザー*> \Application Data\Microsoft\\[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]\Deployment です。</span><span class="sxs-lookup"><span data-stu-id="18375-105">Installation logs are located in %SystemDrive%\Documents and Settings\\<*current user*>\Application Data\Microsoft\\[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]\Deployment.</span></span>  
  
-   <span data-ttu-id="18375-106">**ローカル イベント ログ**: ローカル イベント ログで、インストールの進行状況を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="18375-106">**Local event log**: You can track the progress of an installation in the local event log.</span></span> <span data-ttu-id="18375-107">このため、カスタムのインストール動作をサーバー単位で追跡できます。</span><span class="sxs-lookup"><span data-stu-id="18375-107">Therefore, you can track custom installation actions on a per-server basis.</span></span>  
  
-   <span data-ttu-id="18375-108">**Windows インストーラーのログ**: Microsoft Windows インストーラーが、カスタム アクションのアクション ログに記録するローカル コンピューター上のログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="18375-108">**Windows Installer log**: Microsoft Windows Installer creates a log file on the local computer that logs the actions of a custom action.</span></span> <span data-ttu-id="18375-109">このログ ファイルは、msiexec コマンドの /log オプションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="18375-109">You can specify this log file by using the /log option of the msiexec command.</span></span> <span data-ttu-id="18375-110">詳細については、Windows インストーラーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="18375-110">For more information, see the documentation for Windows Installer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="18375-111">プロパティ スキーマの展開または展開解除は機密データの公開につながる可能性があり、追跡時に機密情報が公開されてしまう可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="18375-111">Deploying or undeploying a property schema may expose sensitive data, and subsequently expose sensitive information during tracking.</span></span> <span data-ttu-id="18375-112">プロパティ スキーマが含まれているアセンブリを展開または展開解除すると、必ずイベント ビューアーによってイベントが Windows アプリケーション イベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="18375-112">Whenever an assembly containing a property schema is deployed or undeployed, the event viewer logs an event in the Windows Application Event Log.</span></span> <span data-ttu-id="18375-113">イベント ログに記録されているメッセージを調べて、すべてのアセンブリ展開アクティビティが機密データに関するポリシーに従っていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18375-113">You should check the event log for these messages to ensure that all assembly deployment activities are in line with your policies for any sensitive data.</span></span> <span data-ttu-id="18375-114">(展開に関してイベント ログに生成されるメッセージ:「ユーザー「{1}」には、"{0}"プロパティのスキーマを含んでいるアセンブリが展開されている」です。</span><span class="sxs-lookup"><span data-stu-id="18375-114">(The message generated to the Event Log for deployment is: "The user "{1}" deployed the assembly "{0}" containing property schemas."</span></span> <span data-ttu-id="18375-115">展開解除に関してイベント ログに生成されるメッセージ:「「{1}」ユーザーは、"{0}"プロパティのスキーマを含んでいるアセンブリを展開解除」です)。</span><span class="sxs-lookup"><span data-stu-id="18375-115">The message generated to the Event Log for undeployment is: "The user "{1}" undeployed the assembly "{0}" containing property schemas.")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18375-116">参照</span><span class="sxs-lookup"><span data-stu-id="18375-116">See Also</span></span>  
 [<span data-ttu-id="18375-117">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="18375-117">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)