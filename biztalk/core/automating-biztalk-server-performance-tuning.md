---
title: BizTalk Server の自動化のパフォーマンス チューニング |Microsoft ドキュメント
description: BTSTask を使用して、インポートまたは BizTalk Server で環境間でのパフォーマンス設定をエクスポートするには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07ff73b5-25d9-4f3f-9a4b-127c0b843741
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e4ea364345ed9f2a8f642e11650cfcd9d09f10f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230354"
---
# <a name="automate-biztalk-server-performance-tuning"></a><span data-ttu-id="ff302-103">BizTalk Server の自動化のパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="ff302-103">Automate BizTalk Server Performance Tuning</span></span>

## <a name="overview"></a><span data-ttu-id="ff302-104">概要</span><span class="sxs-lookup"><span data-stu-id="ff302-104">Overview</span></span>
<span data-ttu-id="ff302-105">チューニングを自動化する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス設定のインポートまたは BizTalk の設定をエクスポートするかを使用して設定を操作することによって[WMI](http://go.microsoft.com/fwlink/?LinkId=200464)です。</span><span class="sxs-lookup"><span data-stu-id="ff302-105">You can automate the tuning of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance settings either by importing or exporting the BizTalk settings or by manipulating the settings using [WMI](http://go.microsoft.com/fwlink/?LinkId=200464).</span></span>  
  
 <span data-ttu-id="ff302-106">最適なパフォーマンスが得られるように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を設定した後、BizTalk Server 設定を XML ファイルにエクスポートまたはインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ff302-106">After the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is set up for optimum performance, you can export or import the BizTalk Server settings to an XML file.</span></span> <span data-ttu-id="ff302-107">BizTalk Server の設定は、設定ダッシュボードまたは BTSTask コマンドライン ユーティリティを使用してインポート/エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ff302-107">You can import/export the BizTalk Server settings either using the Settings Dashboard or the BTSTask command-line utility.</span></span> <span data-ttu-id="ff302-108">**BTSTask.exe**で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]により、BizTalk 管理者は新しいスクリプトを作成するときに BTSTask コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ff302-108">**BTSTask.exe** with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] allows BizTalk administrators to use BTSTask commands when creating new scripts.</span></span>  
  
 <span data-ttu-id="ff302-109">インポート/エクスポート BizTalk Server 設定について 1 つの環境から別の使用に[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]を参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)です。</span><span class="sxs-lookup"><span data-stu-id="ff302-109">For information about importing/exporting BizTalk Server settings from one environment to another using [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="ff302-110">次の手順</span><span class="sxs-lookup"><span data-stu-id="ff302-110">Next steps</span></span> 
  
-   [<span data-ttu-id="ff302-111">インポートまたは BTSTask を使用して BizTalk の設定のエクスポート</span><span class="sxs-lookup"><span data-stu-id="ff302-111">Import or export BizTalk Settings Using BTSTask</span></span>](../core/how-to-import-biztalk-settings-using-btstask.md)  
  
- [<span data-ttu-id="ff302-112">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="ff302-112">BTSTask Command-Line Reference</span></span>](btstask-command-line-reference.md)
  
## <a name="see-also"></a><span data-ttu-id="ff302-113">参照</span><span class="sxs-lookup"><span data-stu-id="ff302-113">See Also</span></span>  
 [<span data-ttu-id="ff302-114">BizTalk Server パフォーマンス設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="ff302-114">Managing BizTalk Server Performance Settings</span></span>](../core/managing-biztalk-server-performance-settings.md)