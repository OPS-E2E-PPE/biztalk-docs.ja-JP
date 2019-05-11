---
title: 追跡プロファイルの展開ユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d631b7c-a40f-4cee-88a4-3d932ab7fde0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf72709c0527b9bc39b238be6d2ca98b698530fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313806"
---
# <a name="tracking-profile-deployment-utility"></a><span data-ttu-id="0f1d3-102">追跡プロファイルの展開ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="0f1d3-102">Tracking Profile Deployment Utility</span></span>
<span data-ttu-id="0f1d3-103">開発者は、bttdeploy ユーティリティを使用する追跡プロファイルを適用し、BAM インフラストラクチャから削除できます。</span><span class="sxs-lookup"><span data-stu-id="0f1d3-103">Developers use the bttdeploy utility to apply tracking profiles to and remove them from the BAM infrastructure.</span></span> <span data-ttu-id="0f1d3-104">Bttdeploy ユーティリティを使用しては、機能的には追跡プロファイル エディター (TPE) で追跡プロファイルの適用 メニュー オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f1d3-104">Using the bttdeploy utility is functionally equivalent to clicking the Apply Tracking Profile menu option in the Tracking Profile Editor (TPE).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f1d3-105">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f1d3-105">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
 <span data-ttu-id="0f1d3-106">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="0f1d3-106">**Usage**</span></span>  
  
 <span data-ttu-id="0f1d3-107">**bttdeploy.exe [options] file name**</span><span class="sxs-lookup"><span data-stu-id="0f1d3-107">**bttdeploy.exe [options] file name**</span></span>  
  
|<span data-ttu-id="0f1d3-108">オプション</span><span class="sxs-lookup"><span data-stu-id="0f1d3-108">Option</span></span>|<span data-ttu-id="0f1d3-109">説明</span><span class="sxs-lookup"><span data-stu-id="0f1d3-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0f1d3-110">/h または/でしょうか。</span><span class="sxs-lookup"><span data-stu-id="0f1d3-110">/h or /?</span></span>|<span data-ttu-id="0f1d3-111">省略可能:Bttdeploy の構文を表示します。</span><span class="sxs-lookup"><span data-stu-id="0f1d3-111">Optional: Displays the syntax summary for bttdeploy.</span></span>|  
|<span data-ttu-id="0f1d3-112">/mgdb \<server name[,port]\>\\<database name\></span><span class="sxs-lookup"><span data-stu-id="0f1d3-112">/mgdb \<server name[,port]\>\\<database name\></span></span>|<span data-ttu-id="0f1d3-113">省略可能:管理サーバー、ポート、およびプロファイルの適用先となるデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f1d3-113">Optional: Specifies the management server, port, and database name to which to apply the profile.</span></span> <span data-ttu-id="0f1d3-114">**注:** このパラメーターを使用する場合、ポートは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0f1d3-114">**Note:**  When using this parameter, the port is optional.</span></span>|  
|<span data-ttu-id="0f1d3-115">/remove と入力し</span><span class="sxs-lookup"><span data-stu-id="0f1d3-115">/remove</span></span>|<span data-ttu-id="0f1d3-116">省略可能:追跡プロファイルを BAM データベースから削除することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f1d3-116">Optional: Specifies that the tracking profile is to be removed from the BAM database.</span></span>|  
|<span data-ttu-id="0f1d3-117">filename</span><span class="sxs-lookup"><span data-stu-id="0f1d3-117">filename</span></span>|<span data-ttu-id="0f1d3-118">追跡の名前はプロファイルを適用または削除するファイルです。</span><span class="sxs-lookup"><span data-stu-id="0f1d3-118">The name of the tracking profile file to apply or remove.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f1d3-119">参照</span><span class="sxs-lookup"><span data-stu-id="0f1d3-119">See Also</span></span>  
 <span data-ttu-id="0f1d3-120">[追跡プロファイル エディター](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="0f1d3-120">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="0f1d3-121">孤立した追跡プロファイルを削除する方法</span><span class="sxs-lookup"><span data-stu-id="0f1d3-121">How to Remove Orphaned Tracking Profiles</span></span>](../core/how-to-remove-orphaned-tracking-profiles.md)