---
title: "追跡プロファイルの展開ユーティリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d631b7c-a40f-4cee-88a4-3d932ab7fde0
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 672879df2c1c5217d8a9710dad000609dd95d0c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="tracking-profile-deployment-utility"></a><span data-ttu-id="66493-102">追跡プロファイルの展開ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="66493-102">Tracking Profile Deployment Utility</span></span>
<span data-ttu-id="66493-103">開発者は、bttdeploy ユーティリティを使用して、追跡プロファイルを BAM インフラストラクチャに適用したり、追跡プロファイルを BAM インフラストラクチャから削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="66493-103">Developers use the bttdeploy utility to apply tracking profiles to and remove them from the BAM infrastructure.</span></span> <span data-ttu-id="66493-104">追跡プロファイル エディター (TPE) で、[追跡プロファイルの適用] メニュー オプションをクリックしても、bttdeploy ユーティリティと同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="66493-104">Using the bttdeploy utility is functionally equivalent to clicking the Apply Tracking Profile menu option in the Tracking Profile Editor (TPE).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66493-105">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="66493-105">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
 <span data-ttu-id="66493-106">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="66493-106">**Usage**</span></span>  
  
 <span data-ttu-id="66493-107">**bttdeploy.exe [オプション] のファイル名**</span><span class="sxs-lookup"><span data-stu-id="66493-107">**bttdeploy.exe [options] file name**</span></span>  
  
|<span data-ttu-id="66493-108">オプション</span><span class="sxs-lookup"><span data-stu-id="66493-108">Option</span></span>|<span data-ttu-id="66493-109">Description</span><span class="sxs-lookup"><span data-stu-id="66493-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="66493-110">/h または /?</span><span class="sxs-lookup"><span data-stu-id="66493-110">/h or /?</span></span>|<span data-ttu-id="66493-111">省略可能: bttdeploy の構文を表示します。</span><span class="sxs-lookup"><span data-stu-id="66493-111">Optional: Displays the syntax summary for bttdeploy.</span></span>|  
|<span data-ttu-id="66493-112">/mgdb\<サーバー名 [, ポート]\>\\< データベース名\></span><span class="sxs-lookup"><span data-stu-id="66493-112">/mgdb \<server name[,port]\>\\<database name\></span></span>|<span data-ttu-id="66493-113">省略可能: 管理サーバー、ポート、およびプロファイルを適用するデータベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="66493-113">Optional: Specifies the management server, port, and database name to which to apply the profile.</span></span> <span data-ttu-id="66493-114">**注:**このパラメーターを使用する場合、ポートは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="66493-114">**Note:**  When using this parameter, the port is optional.</span></span>|  
|<span data-ttu-id="66493-115">/remove</span><span class="sxs-lookup"><span data-stu-id="66493-115">/remove</span></span>|<span data-ttu-id="66493-116">省略可能: は、追跡プロファイルは、BAM データベースから削除することを指定します。</span><span class="sxs-lookup"><span data-stu-id="66493-116">Optional: Specifies that the tracking profile is to be removed from the BAM database.</span></span>|  
|<span data-ttu-id="66493-117">filename</span><span class="sxs-lookup"><span data-stu-id="66493-117">filename</span></span>|<span data-ttu-id="66493-118">適用または削除する追跡プロファイルのファイル名です。</span><span class="sxs-lookup"><span data-stu-id="66493-118">The name of the tracking profile file to apply or remove.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66493-119">参照</span><span class="sxs-lookup"><span data-stu-id="66493-119">See Also</span></span>  
 <span data-ttu-id="66493-120">[追跡プロファイル エディター](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="66493-120">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="66493-121">孤立した追跡プロファイルを削除する方法</span><span class="sxs-lookup"><span data-stu-id="66493-121">How to Remove Orphaned Tracking Profiles</span></span>](../core/how-to-remove-orphaned-tracking-profiles.md)