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
ms.openlocfilehash: b276b9527371b170f15bfed212470ea52bb98eb2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387027"
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a><span data-ttu-id="30008-102">処理前または処理後のスクリプトの送信先を変更する方法</span><span class="sxs-lookup"><span data-stu-id="30008-102">How to Change the Destination Location of a Pre- or Post-processing Script</span></span>
<span data-ttu-id="30008-103">このトピックでは、BizTalk Server 管理コンソールを使用して、前または処理後のスクリプトの送信先を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="30008-103">This topic describes how to use the BizTalk Server Administration console to change the destination location of a pre- or post-processing script.</span></span> <span data-ttu-id="30008-104">これは、アプリケーションがインストールされている場合に、スクリプトをコピーする場所です。</span><span class="sxs-lookup"><span data-stu-id="30008-104">This is the location to which the script is copied when the application is installed.</span></span> <span data-ttu-id="30008-105">別の環境にアプリケーションをデプロイするときに、先の場所を変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="30008-105">You might want to change the destination location when deploying an application into a different environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="30008-106">アプリケーションのアンインストール時に実行するスクリプトの保存先を指定してください。</span><span class="sxs-lookup"><span data-stu-id="30008-106">Be sure to provide a destination location for a script that will run when the application is uninstalled.</span></span> <span data-ttu-id="30008-107">そうでない場合、スクリプトは、ローカル ファイル システムにはコピーされず、そのため、アンインストール中には実行されません。</span><span class="sxs-lookup"><span data-stu-id="30008-107">If you do not, the script will not be copied to the local file system, and therefore will not run during uninstallation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="30008-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="30008-108">Prerequisites</span></span>  
 <span data-ttu-id="30008-109">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30008-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="30008-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="30008-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a><span data-ttu-id="30008-111">処理前または処理後のスクリプトの展開プロパティを変更するには</span><span class="sxs-lookup"><span data-stu-id="30008-111">To modify the deployment properties of a pre- or post-processing script</span></span>  
  
1. <span data-ttu-id="30008-112">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="30008-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="30008-113">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を変更するスクリプトが含まれる BizTalk グループを展開し、スクリプトが含まれるアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="30008-113">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the script to modify, and then expand the application containing the script.</span></span>  
  
3. <span data-ttu-id="30008-114">をクリックして、**リソース**フォルダーは、スクリプトを右クリックし、順にクリックします**変更**します。</span><span class="sxs-lookup"><span data-stu-id="30008-114">Click the **Resources** folder, right-click the script, and then click **Modify**.</span></span>  
  
4. <span data-ttu-id="30008-115">**先**ファイル名を含めて、先の場所の完全なパスを入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="30008-115">In **Destination location**, type the full path of the destination location, including the file name, and then click **OK**.</span></span> <span data-ttu-id="30008-116">(を使用できます、環境変数 %btad_installdir% パスでアプリケーションのインストール フォルダーを指定するのに)。</span><span class="sxs-lookup"><span data-stu-id="30008-116">(You can use the environment variable %BTAD_InstallDir% in the path to specify the application installation folder.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30008-117">参照</span><span class="sxs-lookup"><span data-stu-id="30008-117">See Also</span></span>  
 [<span data-ttu-id="30008-118">処理前および処理後のスクリプトの管理</span><span class="sxs-lookup"><span data-stu-id="30008-118">Managing Pre- and Post-processing Scripts</span></span>](../core/managing-pre-and-post-processing-scripts.md)