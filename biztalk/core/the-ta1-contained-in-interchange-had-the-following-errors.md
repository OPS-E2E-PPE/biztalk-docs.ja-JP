---
title: TA1 インターチェンジに含まれる次のエラーが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d63fe9-63ef-44b3-8cb9-45a7abf8d0e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6ce98988b8e52b808a5deaa9a8199bb37deb85e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254342"
---
# <a name="the-ta1-contained-in-interchange-had-the-following-errors"></a><span data-ttu-id="78290-102">TA1 インターチェンジに含まれる次のエラーが</span><span class="sxs-lookup"><span data-stu-id="78290-102">The TA1 contained in interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="78290-103">詳細</span><span class="sxs-lookup"><span data-stu-id="78290-103">Details</span></span>  
  
|                 |                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="78290-104">製品名</span><span class="sxs-lookup"><span data-stu-id="78290-104">Product Name</span></span>   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| <span data-ttu-id="78290-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="78290-105">Product Version</span></span> |                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    <span data-ttu-id="78290-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="78290-106">Event ID</span></span>     |                                                        -                                                         |
|  <span data-ttu-id="78290-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="78290-107">Event Source</span></span>   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="78290-108">EDI</span><span class="sxs-lookup"><span data-stu-id="78290-108">EDI</span></span>              |
|    <span data-ttu-id="78290-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="78290-109">Component</span></span>    |                                                    <span data-ttu-id="78290-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="78290-110">EDI Engine</span></span>                                                    |
|  <span data-ttu-id="78290-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="78290-111">Symbolic Name</span></span>  |                                                   <span data-ttu-id="78290-112">X12TA1Error</span><span class="sxs-lookup"><span data-stu-id="78290-112">X12TA1Error</span></span>                                                    |
|  <span data-ttu-id="78290-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="78290-113">Message Text</span></span>   | <span data-ttu-id="78290-114">{0} Id を持つインターチェンジに含まれている TA1 '{1}'、送信者 id'{2}'、受信者 id '{3}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="78290-114">The {0} TA1 contained in interchange with id '{1}', sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="78290-115">説明</span><span class="sxs-lookup"><span data-stu-id="78290-115">Explanation</span></span>  
 <span data-ttu-id="78290-116">このエラー/警告/情報イベントは、受信パイプラインが表示されているエラー状態のため受信 TA1 受信確認を処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="78290-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming TA1 acknowledgment because of the indicated error condition.</span></span> <span data-ttu-id="78290-117">受信確認が TA1Schema に準拠していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78290-117">This may indicate that the acknowledgment does not conform to the TA1Schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="78290-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="78290-118">User Action</span></span>  
 <span data-ttu-id="78290-119">このエラーを解決するには、受信確認が、TA1Schema に準拠していることを確認、受信確認で問題を解決して、受信確認を再送信して、受信確認の送信者を依頼します。</span><span class="sxs-lookup"><span data-stu-id="78290-119">To resolve this error, have the sender of the acknowledgment resolve the issue with the acknowledgment, ensuring that the acknowledgment conforms to the TA1Schema, and then resend the acknowledgment.</span></span>