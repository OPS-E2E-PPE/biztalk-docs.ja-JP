---
title: "BizTalk ビジネス アクティビティの監視が構成されていない EDI AS2 状態レポートの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f46c1c8-2771-4b16-8fb1-71952792ac4a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e84301e55cd6fbdcb74467758c7e338e61b727f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-business-activity-monitoring-has-not-been-configured-for-edi-as2-status-reporting"></a><span data-ttu-id="aac80-102">BizTalk ビジネス アクティビティの監視が構成されていない EDI AS2 状態レポート用</span><span class="sxs-lookup"><span data-stu-id="aac80-102">BizTalk Business Activity Monitoring has not been configured for EDI-AS2 status reporting</span></span>
## <a name="details"></a><span data-ttu-id="aac80-103">詳細</span><span class="sxs-lookup"><span data-stu-id="aac80-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aac80-104">製品名</span><span class="sxs-lookup"><span data-stu-id="aac80-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="aac80-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="aac80-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="aac80-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aac80-106">Event ID</span></span>|-|  
|<span data-ttu-id="aac80-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="aac80-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="aac80-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="aac80-108"> EDI</span></span>|  
|<span data-ttu-id="aac80-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aac80-109">Component</span></span>|<span data-ttu-id="aac80-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="aac80-110">AS2 Engine</span></span>|  
|<span data-ttu-id="aac80-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="aac80-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="aac80-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="aac80-112">Message Text</span></span>|<span data-ttu-id="aac80-113">EDI および AS2 状態レポート用 BizTalk ビジネス アクティビティの監視が構成されていません。</span><span class="sxs-lookup"><span data-stu-id="aac80-113">BizTalk Business Activity Monitoring has not been configured for EDI/AS2 status reporting.</span></span> <span data-ttu-id="aac80-114">したがって状態レポート機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="aac80-114">Hence status reporting feature will be disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aac80-115">説明</span><span class="sxs-lookup"><span data-stu-id="aac80-115">Explanation</span></span>  
 <span data-ttu-id="aac80-116">このエラー/警告/情報イベントは、ビジネス アクティビティの監視 (BAM) が BizTalk 構成ウィザードを使用して構成されていないため、EDI/AS2 状態レポート機能が有効になっていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="aac80-116">This Error/Warning/Information event indicates that EDI/AS2 status reporting is not enabled because Business Activity Monitoring (BAM) has not been configured through the BizTalk Configuration Wizard.</span></span> <span data-ttu-id="aac80-117">EDI/AS2 状態レポート機能を使用するには BAM インフラストラクチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="aac80-117">The BAM infrastructure is a prerequisite for EDI/AS2 status reporting.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aac80-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="aac80-118">User Action</span></span>  
 <span data-ttu-id="aac80-119">このエラーを解決するには、BizTalk 構成ウィザードを実行し、ビジネス アクティビティの監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="aac80-119">To resolve this error, run the BizTalk Configuration Wizard and configure Business Activity Monitoring.</span></span>