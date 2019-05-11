---
title: 不明または無効なトランザクション セット識別子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 282c8128-7d23-44e2-bf44-e90e52cb5fb1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9dca8c7d26eb826ff6da339ae77040e5527238c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324517"
---
# <a name="missing-or-invalid-transaction-set-identifier"></a><span data-ttu-id="e60a3-102">トランザクション セット識別子が見つからないか無効です</span><span class="sxs-lookup"><span data-stu-id="e60a3-102">Missing or invalid Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="e60a3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e60a3-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e60a3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e60a3-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e60a3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e60a3-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e60a3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e60a3-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e60a3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e60a3-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e60a3-108">EDI</span><span class="sxs-lookup"><span data-stu-id="e60a3-108">EDI</span></span> |
|    <span data-ttu-id="e60a3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e60a3-109">Component</span></span>    |                                       <span data-ttu-id="e60a3-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e60a3-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e60a3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e60a3-111">Symbolic Name</span></span>  |                     <span data-ttu-id="e60a3-112">EfactTsMissingOrInvalidTsIdentiferDescription</span><span class="sxs-lookup"><span data-stu-id="e60a3-112">EfactTsMissingOrInvalidTsIdentiferDescription</span></span>                      |
|  <span data-ttu-id="e60a3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e60a3-113">Message Text</span></span>   |                     <span data-ttu-id="e60a3-114">トランザクション セット識別子が見つからないか無効です</span><span class="sxs-lookup"><span data-stu-id="e60a3-114">Missing or invalid Transaction set identifier</span></span>                      |
  
## <a name="explanation"></a><span data-ttu-id="e60a3-115">説明</span><span class="sxs-lookup"><span data-stu-id="e60a3-115">Explanation</span></span>  
 <span data-ttu-id="e60a3-116">このエラー/警告/情報イベントは、トランザクション セット ID の値 (UNH2.1 フィールド) がないか、値が無効であったため、受信または送信パイプラインで EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e60a3-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the EDIFACT interchange because the value of the transaction set identifier (in the UNH2.1 field) was missing or had an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e60a3-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e60a3-117">User Action</span></span>  
 <span data-ttu-id="e60a3-118">このエラーを解決するには、インターチェンジの UNH2.1 フィールドに値が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e60a3-118">To resolve this error, make sure that the interchange has a value for the UNH2.1 field.</span></span> <span data-ttu-id="e60a3-119">UNH2.1 の値が、ドキュメントの種類を示す有効な 1 桁から 6 桁の指定子であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e60a3-119">Verify that the value of UNH2.1 is a valid one-digit to six-digit document-type designator.</span></span>