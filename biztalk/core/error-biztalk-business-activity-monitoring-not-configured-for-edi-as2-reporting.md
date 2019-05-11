---
title: BizTalk ビジネス アクティビティの監視が構成されていない EDI AS2 状態レポート用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f46c1c8-2771-4b16-8fb1-71952792ac4a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58b6326829f6077b52acdca24d87b81acb3bc481
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349039"
---
# <a name="biztalk-business-activity-monitoring-has-not-been-configured-for-edi-as2-status-reporting"></a><span data-ttu-id="1268b-102">BizTalk ビジネス アクティビティの監視が構成されていない EDI AS2 状態レポート用</span><span class="sxs-lookup"><span data-stu-id="1268b-102">BizTalk Business Activity Monitoring has not been configured for EDI-AS2 status reporting</span></span>
## <a name="details"></a><span data-ttu-id="1268b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1268b-103">Details</span></span>  
  
|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1268b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1268b-104">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| <span data-ttu-id="1268b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1268b-105">Product Version</span></span> |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    <span data-ttu-id="1268b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1268b-106">Event ID</span></span>     |                                                                      -                                                                      |
|  <span data-ttu-id="1268b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1268b-107">Event Source</span></span>   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1268b-108">EDI</span><span class="sxs-lookup"><span data-stu-id="1268b-108">EDI</span></span>                            |
|    <span data-ttu-id="1268b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1268b-109">Component</span></span>    |                                                                 <span data-ttu-id="1268b-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="1268b-110">AS2 Engine</span></span>                                                                  |
|  <span data-ttu-id="1268b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1268b-111">Symbolic Name</span></span>  |                                                                      -                                                                      |
|  <span data-ttu-id="1268b-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1268b-112">Message Text</span></span>   | <span data-ttu-id="1268b-113">EDI および AS2 状態レポート用 BizTalk ビジネス アクティビティの監視が構成されていません。</span><span class="sxs-lookup"><span data-stu-id="1268b-113">BizTalk Business Activity Monitoring has not been configured for EDI/AS2 status reporting.</span></span> <span data-ttu-id="1268b-114">そのため、状態レポート機能を無効化されます。</span><span class="sxs-lookup"><span data-stu-id="1268b-114">Hence status reporting feature will be disabled.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1268b-115">説明</span><span class="sxs-lookup"><span data-stu-id="1268b-115">Explanation</span></span>  
 <span data-ttu-id="1268b-116">このエラー/警告/情報イベントは、EDI および AS2 状態レポートが無効である BizTalk 構成ウィザードを使ってビジネス アクティビティ監視 (BAM) が構成されていないためにことを示します。</span><span class="sxs-lookup"><span data-stu-id="1268b-116">This Error/Warning/Information event indicates that EDI/AS2 status reporting is not enabled because Business Activity Monitoring (BAM) has not been configured through the BizTalk Configuration Wizard.</span></span> <span data-ttu-id="1268b-117">BAM インフラストラクチャは、EDI および AS2 状態レポートの前提条件です。</span><span class="sxs-lookup"><span data-stu-id="1268b-117">The BAM infrastructure is a prerequisite for EDI/AS2 status reporting.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1268b-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1268b-118">User Action</span></span>  
 <span data-ttu-id="1268b-119">このエラーを解決するのには、BizTalk 構成ウィザードを実行し、ビジネス アクティビティの監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="1268b-119">To resolve this error, run the BizTalk Configuration Wizard and configure Business Activity Monitoring.</span></span>