---
title: 処理前または処理後のスクリプトの送信先を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, file locations
- scripts, modifying
- managing [scripts], modifying
- managing [scripts], file locations
ms.assetid: 4a4fdaef-099f-4c29-9815-12404c7a2212
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6d1a7ec9f661a86ff028b1ec364bbd656cbb2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005291"
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a><span data-ttu-id="c22cd-102">処理前または処理後のスクリプトの送信先を変更する方法</span><span class="sxs-lookup"><span data-stu-id="c22cd-102">How to Change the Destination Location of a Pre- or Post-processing Script</span></span>
<span data-ttu-id="c22cd-103">このトピックでは、BizTalk Server 管理コンソールを使用して、処理前または処理後のスクリプトの送信先を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c22cd-103">This topic describes how to use the BizTalk Server Administration console to change the destination location of a pre- or post-processing script.</span></span> <span data-ttu-id="c22cd-104">これは、アプリケーションをインストールするときにスクリプトがコピーされる場所です。</span><span class="sxs-lookup"><span data-stu-id="c22cd-104">This is the location to which the script is copied when the application is installed.</span></span> <span data-ttu-id="c22cd-105">アプリケーションを別の環境に展開するときは、送信先を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c22cd-105">You might want to change the destination location when deploying an application into a different environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c22cd-106">アプリケーションのアンインストール時に実行するスクリプトに、送信先を指定してください。</span><span class="sxs-lookup"><span data-stu-id="c22cd-106">Be sure to provide a destination location for a script that will run when the application is uninstalled.</span></span> <span data-ttu-id="c22cd-107">指定しないと、スクリプトはローカル ファイル システムにコピーされず、したがってアンインストール時に実行されません。</span><span class="sxs-lookup"><span data-stu-id="c22cd-107">If you do not, the script will not be copied to the local file system, and therefore will not run during uninstallation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c22cd-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="c22cd-108">Prerequisites</span></span>  
 <span data-ttu-id="c22cd-109">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c22cd-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c22cd-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="c22cd-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a><span data-ttu-id="c22cd-111">処理前または処理後のスクリプトの展開プロパティを変更するには</span><span class="sxs-lookup"><span data-stu-id="c22cd-111">To modify the deployment properties of a pre- or post-processing script</span></span>  
  
1. <span data-ttu-id="c22cd-112">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="c22cd-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c22cd-113">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、変更するスクリプトが含まれる BizTalk グループ、スクリプトが含まれるアプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="c22cd-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the script to modify, and then expand the application containing the script.</span></span>  
  
3. <span data-ttu-id="c22cd-114">をクリックして、**リソース**フォルダーは、スクリプトを右クリックし、順にクリックします**変更**します。</span><span class="sxs-lookup"><span data-stu-id="c22cd-114">Click the **Resources** folder, right-click the script, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="c22cd-115">**先**ファイル名を含めて、先の場所の完全なパスを入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c22cd-115">In **Destination location**, type the full path of the destination location, including the file name, and then click **OK**.</span></span> <span data-ttu-id="c22cd-116">アプリケーションのインストール フォルダーを指定するには、パスで環境変数 %BTAD_InstallDir% を使用します。</span><span class="sxs-lookup"><span data-stu-id="c22cd-116">(You can use the environment variable %BTAD_InstallDir% in the path to specify the application installation folder.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22cd-117">参照</span><span class="sxs-lookup"><span data-stu-id="c22cd-117">See Also</span></span>  
 [<span data-ttu-id="c22cd-118">処理前および処理後のスクリプトの管理</span><span class="sxs-lookup"><span data-stu-id="c22cd-118">Managing Pre- and Post-processing Scripts</span></span>](../core/managing-pre-and-post-processing-scripts.md)