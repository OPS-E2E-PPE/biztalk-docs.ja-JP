---
title: BizTalk アプリケーション展開の進行状況の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, deploying
- applications, monitoring
- deploying [applications], monitoring
- monitoring, applications
ms.assetid: a69a8288-0203-440f-9805-52786525e193
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07beea810ff64c807685b8170009d5204ede1af7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001155"
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a><span data-ttu-id="c92fa-102">BizTalk アプリケーション展開の進行状況の監視</span><span class="sxs-lookup"><span data-stu-id="c92fa-102">Monitoring the Progress of Your BizTalk Application Deployment</span></span>
<span data-ttu-id="c92fa-103">BizTalk アプリケーションの展開の進行状況は、2 つの方法で監視できます。</span><span class="sxs-lookup"><span data-stu-id="c92fa-103">You can monitor the progress of your BizTalk application deployment in two ways:</span></span>  
  
- <span data-ttu-id="c92fa-104">**BizTalk インストール ログ**: BizTalk Server が生成するインストール ログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c92fa-104">**BizTalk installation log**: You can consult the installation log that BizTalk Server generates.</span></span> <span data-ttu-id="c92fa-105">インストール ログにある %SystemDrive%\Documents and Settings\\<*現在のユーザー*\>\Application Data\Microsoft\BizTalk Server\Deployment します。</span><span class="sxs-lookup"><span data-stu-id="c92fa-105">Installation logs are located in %SystemDrive%\Documents and Settings\\<*current user*\>\Application Data\Microsoft\BizTalk Server\Deployment.</span></span>  
  
- <span data-ttu-id="c92fa-106">**ローカル イベント ログ**: ローカル イベント ログで、インストールの進行状況を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="c92fa-106">**Local event log**: You can track the progress of an installation in the local event log.</span></span> <span data-ttu-id="c92fa-107">このため、カスタムのインストール動作をサーバー単位で追跡できます。</span><span class="sxs-lookup"><span data-stu-id="c92fa-107">Therefore, you can track custom installation actions on a per-server basis.</span></span>  
  
- <span data-ttu-id="c92fa-108">**Windows インストーラー ログ**: Microsoft Windows インストーラーには、カスタム アクションのアクション ログに記録する、ローカル コンピューター上のログ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c92fa-108">**Windows Installer log**: Microsoft Windows Installer creates a log file on the local computer that logs the actions of a custom action.</span></span> <span data-ttu-id="c92fa-109">このログ ファイルは、msiexec コマンドの /log オプションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="c92fa-109">You can specify this log file by using the /log option of the msiexec command.</span></span> <span data-ttu-id="c92fa-110">詳細については、Windows インストーラーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c92fa-110">For more information, see the documentation for Windows Installer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c92fa-111">プロパティ スキーマの展開または展開解除は機密データの公開につながる可能性があり、追跡時に機密情報が公開されてしまう可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="c92fa-111">Deploying or undeploying a property schema may expose sensitive data, and subsequently expose sensitive information during tracking.</span></span> <span data-ttu-id="c92fa-112">プロパティ スキーマが含まれているアセンブリを展開または展開解除すると、必ずイベント ビューアーによってイベントが Windows アプリケーション イベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c92fa-112">Whenever an assembly containing a property schema is deployed or undeployed, the event viewer logs an event in the Windows Application Event Log.</span></span> <span data-ttu-id="c92fa-113">イベント ログに記録されているメッセージを調べて、すべてのアセンブリ展開アクティビティが機密データに関するポリシーに従っていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c92fa-113">You should check the event log for these messages to ensure that all assembly deployment activities are in line with your policies for any sensitive data.</span></span> <span data-ttu-id="c92fa-114">(展開に関してイベント ログに生成されるメッセージ:"user"{1}「アセンブリの展開」{0}「プロパティのスキーマを格納します」。</span><span class="sxs-lookup"><span data-stu-id="c92fa-114">(The message generated to the Event Log for deployment is: "The user "{1}" deployed the assembly "{0}" containing property schemas."</span></span> <span data-ttu-id="c92fa-115">展開解除は、イベント ログに生成されたメッセージ:"user"{1}「アセンブリの展開を解除」{0}「プロパティのスキーマを格納します」)。</span><span class="sxs-lookup"><span data-stu-id="c92fa-115">The message generated to the Event Log for undeployment is: "The user "{1}" undeployed the assembly "{0}" containing property schemas.")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c92fa-116">参照</span><span class="sxs-lookup"><span data-stu-id="c92fa-116">See Also</span></span>  
 [<span data-ttu-id="c92fa-117">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="c92fa-117">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)