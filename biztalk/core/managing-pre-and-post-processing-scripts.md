---
title: 前処理および後処理のスクリプトの管理 |Microsoft ドキュメント
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
ms.openlocfilehash: 18926a0c51e5ab5f65b32373d20b2931ccaa627d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262474"
---
# <a name="manage-pre--and-post-processing-scripts"></a><span data-ttu-id="45c33-102">前処理および後処理のスクリプトを管理します。</span><span class="sxs-lookup"><span data-stu-id="45c33-102">Manage Pre- and Post-processing Scripts</span></span>

## <a name="overview"></a><span data-ttu-id="45c33-103">概要</span><span class="sxs-lookup"><span data-stu-id="45c33-103">Overview</span></span>
<span data-ttu-id="45c33-104">ここでは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して処理前および処理後のスクリプトを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="45c33-104">This section provides instructions on using the BizTalk Server Administration console or the BTSTask command-line tool to manage pre- and post-processing scripts.</span></span> <span data-ttu-id="45c33-105">BizTalk アプリケーションをインポート、インストール、またはアンインストール (削除) するときに実行するスクリプトを作成して、そのスクリプトをアプリケーションに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="45c33-105">You can create a script that you want to have run when a BizTalk application is imported, installed, or uninstalled (removed), and then add the script to the application.</span></span> <span data-ttu-id="45c33-106">スクリプトを追加する際には、処理前のスクリプト (インポートまたはインストールの前、アンインストールの後に実行) か処理後のスクリプト (インポートまたはインストールの後、およびアンインストールの前に実行) かを指定します。</span><span class="sxs-lookup"><span data-stu-id="45c33-106">When you add a script, you specify whether it is a pre-preprocessing script, which runs before import, installation and after uninstallation, or a post-processing script, which runs after import or installation, and before uninstallation.</span></span>  
  
 <span data-ttu-id="45c33-107">アプリケーションのエクスポート時にスクリプトを選択する場合、スクリプトはアプリケーションの .msi ファイルに組み込みます。</span><span class="sxs-lookup"><span data-stu-id="45c33-107">If you select the script when exporting the application, the script is included in the .msi file for the application.</span></span> <span data-ttu-id="45c33-108">アプリケーションをインストール、アンインストール、またはインポートする際に、スクリプトが記述に従って自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="45c33-108">When you install, uninstall, or import the application, the script automatically runs, depending on how you have written the script.</span></span> <span data-ttu-id="45c33-109">詳細については、作成して、スクリプトを使用して、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="45c33-109">For more information about creating and using scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45c33-110">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="45c33-110">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="45c33-111">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="45c33-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="45c33-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="45c33-112">Next steps</span></span> 
  
-   [<span data-ttu-id="45c33-113">前または処理後のスクリプトをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="45c33-113">Add a Pre- or Post-processing Script to an Application</span></span>](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [<span data-ttu-id="45c33-114">前または処理後のスクリプトの移行先の場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="45c33-114">Change the Destination Location of a Pre- or Post-processing Script</span></span>](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [<span data-ttu-id="45c33-115">前または処理後のスクリプトをアプリケーションから削除します。</span><span class="sxs-lookup"><span data-stu-id="45c33-115">Remove a Pre- or Post-processing Script from an Application</span></span>](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)