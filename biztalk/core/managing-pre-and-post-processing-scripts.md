---
title: 前処理および後処理のスクリプトの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 107ada12-fef2-4b56-8ff8-228c13761104
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b39deb7d053ec21677e519852184550d6f3c793d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328043"
---
# <a name="manage-pre--and-post-processing-scripts"></a><span data-ttu-id="64f30-102">前処理および後処理のスクリプトを管理します。</span><span class="sxs-lookup"><span data-stu-id="64f30-102">Manage Pre- and Post-processing Scripts</span></span>

## <a name="overview"></a><span data-ttu-id="64f30-103">概要</span><span class="sxs-lookup"><span data-stu-id="64f30-103">Overview</span></span>
<span data-ttu-id="64f30-104">このセクションでは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して、前処理および後処理のスクリプトの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="64f30-104">This section provides instructions on using the BizTalk Server Administration console or the BTSTask command-line tool to manage pre- and post-processing scripts.</span></span> <span data-ttu-id="64f30-105">(削除) を BizTalk アプリケーションのインポート、インストール、またはアンインストール時に実行するスクリプトを作成でき、アプリケーションにスクリプトを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="64f30-105">You can create a script that you want to have run when a BizTalk application is imported, installed, or uninstalled (removed), and then add the script to the application.</span></span> <span data-ttu-id="64f30-106">スクリプトを追加するときに、インポート、インストールする前に、アンインストールの後で実行され、処理前のスクリプトまたは実行後、インポートまたはインストールとアンインストールの前に処理後のスクリプトであるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="64f30-106">When you add a script, you specify whether it is a pre-preprocessing script, which runs before import, installation and after uninstallation, or a post-processing script, which runs after import or installation, and before uninstallation.</span></span>  
  
 <span data-ttu-id="64f30-107">アプリケーションをエクスポートするときに、スクリプトを選択した場合、スクリプトは、アプリケーションの .msi ファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="64f30-107">If you select the script when exporting the application, the script is included in the .msi file for the application.</span></span> <span data-ttu-id="64f30-108">インストール、アンインストール、またはアプリケーションをインポートするときに、スクリプトが自動的に実行、に応じてスクリプトを記述する方法。</span><span class="sxs-lookup"><span data-stu-id="64f30-108">When you install, uninstall, or import the application, the script automatically runs, depending on how you have written the script.</span></span> <span data-ttu-id="64f30-109">詳細については、作成して、スクリプトを使用して、次を参照してください。[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="64f30-109">For more information about creating and using scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64f30-110">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="64f30-110">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="64f30-111">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="64f30-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="64f30-112">次のステップ</span><span class="sxs-lookup"><span data-stu-id="64f30-112">Next steps</span></span> 
  
-   [<span data-ttu-id="64f30-113">処理前または処理後のスクリプトをアプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="64f30-113">Add a Pre- or Post-processing Script to an Application</span></span>](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [<span data-ttu-id="64f30-114">処理前または処理後のスクリプトの送信先を変更する</span><span class="sxs-lookup"><span data-stu-id="64f30-114">Change the Destination Location of a Pre- or Post-processing Script</span></span>](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [<span data-ttu-id="64f30-115">処理前または処理後のスクリプトをアプリケーションから削除する</span><span class="sxs-lookup"><span data-stu-id="64f30-115">Remove a Pre- or Post-processing Script from an Application</span></span>](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)