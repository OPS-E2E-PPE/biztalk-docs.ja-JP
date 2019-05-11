---
title: グローバル設定 タブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.globalsettings
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- Global Settings tab [Configuration Explorer]
- auditing, configuring
ms.assetid: 057189f7-9072-4841-950f-371ba1f73a15
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77a883a4d506d3ee65a5ef0edc7ab5dc6495f039
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267980"
---
# <a name="global-settings-tab"></a><span data-ttu-id="dbeb5-102">グローバル設定 タブ</span><span class="sxs-lookup"><span data-stu-id="dbeb5-102">Global Settings Tab</span></span>
<span data-ttu-id="dbeb5-103">使用する、**グローバル設定** タブで使用されるログ ストアを構成する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-103">You use the **Global Settings** tab to configure the logging store used by [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  

 <span data-ttu-id="dbeb5-104">**BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスの 、**グローバル設定** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-104">In the **BTAHL7 Configuration Explorer** dialog box, on the **Global Settings** tab, do the following:</span></span>  


|     <span data-ttu-id="dbeb5-105">プロパティ</span><span class="sxs-lookup"><span data-stu-id="dbeb5-105">Use this</span></span>      |                                                                                                                                                <span data-ttu-id="dbeb5-106">目的</span><span class="sxs-lookup"><span data-stu-id="dbeb5-106">To do this</span></span>                                                                                                                                                |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      <span data-ttu-id="dbeb5-107">**WMI**</span><span class="sxs-lookup"><span data-stu-id="dbeb5-107">**WMI**</span></span>      |                                                                 <span data-ttu-id="dbeb5-108">生成する場合は、このオプションを選択[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]BTAHL7 の Management Instrumentation (WMI) 通知します。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-108">Select this option if you want to generate [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI) notifications for BTAHL7.</span></span>                                                                  |
|      <span data-ttu-id="dbeb5-109">**SQL**</span><span class="sxs-lookup"><span data-stu-id="dbeb5-109">**SQL**</span></span>      | <span data-ttu-id="dbeb5-110">Microsoft を使用する場合は、このオプションを選択[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]BTAHL7 のログ記録ストアとして。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-110">Select this option if you want to use Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] as your logging store for BTAHL7.</span></span> <span data-ttu-id="dbeb5-111">**注:** BTAHL7 では、存在しない場合は、ログに必要なテーブルが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-111">**Note:**  BTAHL7 automatically creates the tables required for logging if they do not exist.</span></span> |
|  <span data-ttu-id="dbeb5-112">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="dbeb5-112">**SQL Server**</span></span>   |            <span data-ttu-id="dbeb5-113">型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-113">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] name.</span></span> <span data-ttu-id="dbeb5-114">これは、選択したときに必要な**SQL**オプション。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-114">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="dbeb5-115">許容最大長は、64 文字です。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-115">The maximum allowed length is 64 characters.</span></span><br /><br /> <span data-ttu-id="dbeb5-116">既定のサーバーとデータベース名は、構成されている BTAHL7 データベースです。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-116">The default server and database name is the configured BTAHL7 database.</span></span>            |
| <span data-ttu-id="dbeb5-117">**データベース名**</span><span class="sxs-lookup"><span data-stu-id="dbeb5-117">**Database name**</span></span> |                                                 <span data-ttu-id="dbeb5-118">型、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース名。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-118">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database name.</span></span> <span data-ttu-id="dbeb5-119">これは、選択したときに必要な**SQL**オプション。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-119">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="dbeb5-120">許容最大長は 128 文字です。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-120">The maximum allowed length is 128 characters.</span></span>                                                 |
|   <span data-ttu-id="dbeb5-121">**イベント ログ**</span><span class="sxs-lookup"><span data-stu-id="dbeb5-121">**Event Log**</span></span>   |                <span data-ttu-id="dbeb5-122">使用する場合は、このオプションを選択、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] BTAHL7 のログ記録ストアとしてのイベント ログ。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-122">Select this option if you want to use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log as the logging store for BTAHL7.</span></span> <span data-ttu-id="dbeb5-123">使用する、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアーでイベント メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="dbeb5-123">You use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer to view event messages.</span></span>                 |

