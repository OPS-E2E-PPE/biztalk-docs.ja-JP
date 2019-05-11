---
title: 見つからないか無効か重複するトランザクション セット識別子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8580aab2-9fa4-43fb-b643-10621926591e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2165168f092dfb2e3b82116b1fb32153b5f4551f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324598"
---
# <a name="missing-or-invalid-or-duplicate-transaction-set-identifier"></a><span data-ttu-id="02a16-102">見つからないか無効か重複するトランザクション セット識別子</span><span class="sxs-lookup"><span data-stu-id="02a16-102">Missing or invalid or duplicate Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="02a16-103">詳細</span><span class="sxs-lookup"><span data-stu-id="02a16-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="02a16-104">製品名</span><span class="sxs-lookup"><span data-stu-id="02a16-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="02a16-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="02a16-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="02a16-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="02a16-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="02a16-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="02a16-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="02a16-108">EDI</span><span class="sxs-lookup"><span data-stu-id="02a16-108">EDI</span></span> |
|    <span data-ttu-id="02a16-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="02a16-109">Component</span></span>    |                                       <span data-ttu-id="02a16-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="02a16-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="02a16-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="02a16-111">Symbolic Name</span></span>  |                      <span data-ttu-id="02a16-112">X12TsMissingOrInvalidTsIdentiferDescription2</span><span class="sxs-lookup"><span data-stu-id="02a16-112">X12TsMissingOrInvalidTsIdentiferDescription2</span></span>                      |
|  <span data-ttu-id="02a16-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="02a16-113">Message Text</span></span>   |            <span data-ttu-id="02a16-114">見つからないか無効か重複するトランザクション セット識別子 '{0}'</span><span class="sxs-lookup"><span data-stu-id="02a16-114">Missing or invalid or duplicate Transaction set identifier '{0}'</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="02a16-115">説明</span><span class="sxs-lookup"><span data-stu-id="02a16-115">Explanation</span></span>  
 <span data-ttu-id="02a16-116">このエラー/警告/情報イベントは、トランザクション セット ID の値 (ST01 フィールド) がないか、重複していたか、値が無効であったため、受信または送信パイプラインで X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="02a16-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the X12 interchange because the value of the transaction set identifier (in the ST01 field) was missing, a duplicate, or had an invalid value.</span></span> <span data-ttu-id="02a16-117">このエラーが発生する場合は、ドキュメント スキーマに ST ヘッダーと SE トレーラーがない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02a16-117">This can occur if the document schema does not have an ST header and an SE trailer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="02a16-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="02a16-118">User Action</span></span>  
 <span data-ttu-id="02a16-119">このエラーを解決するには、インターチェンジに ST01 フィールドの値があり、スキーマに ST ヘッダーと SE トレーラーのエントリがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="02a16-119">To resolve this error, make sure that the interchange has a value for the ST01 field and that the schema has an entry for the ST header and SE trailer.</span></span> <span data-ttu-id="02a16-120">ST01 の値が、3 桁の有効なドキュメント型の識別子であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="02a16-120">Verify that the value of ST01 is a valid three-digit document-type designator.</span></span> <span data-ttu-id="02a16-121">ST01 フィールドが、別のトランザクション セットの ST01 フィールドと重複していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="02a16-121">Verify that the ST01 field is not a duplicate with the ST01 field of another transaction set.</span></span>