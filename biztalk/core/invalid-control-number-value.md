---
title: 無効な制御番号の値 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ac762e2-2d48-45e8-b4c4-2df246b7568c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b426d7bb5834dac14f3bc1db24f62a40eb71ffb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330840"
---
# <a name="invalid-control-number-value"></a><span data-ttu-id="780ec-102">制御番号の値が無効です</span><span class="sxs-lookup"><span data-stu-id="780ec-102">Invalid Control Number Value</span></span>
## <a name="details"></a><span data-ttu-id="780ec-103">詳細</span><span class="sxs-lookup"><span data-stu-id="780ec-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="780ec-104">製品名</span><span class="sxs-lookup"><span data-stu-id="780ec-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="780ec-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="780ec-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="780ec-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="780ec-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="780ec-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="780ec-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="780ec-108">EDI</span><span class="sxs-lookup"><span data-stu-id="780ec-108">EDI</span></span> |
|    <span data-ttu-id="780ec-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="780ec-109">Component</span></span>    |                                       <span data-ttu-id="780ec-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="780ec-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="780ec-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="780ec-111">Symbolic Name</span></span>  |                       <span data-ttu-id="780ec-112">X12Ta1InvalidControlNumberValueDescription</span><span class="sxs-lookup"><span data-stu-id="780ec-112">X12Ta1InvalidControlNumberValueDescription</span></span>                       |
|  <span data-ttu-id="780ec-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="780ec-113">Message Text</span></span>   |                              <span data-ttu-id="780ec-114">制御番号の値が無効です</span><span class="sxs-lookup"><span data-stu-id="780ec-114">Invalid Control Number Value</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="780ec-115">説明</span><span class="sxs-lookup"><span data-stu-id="780ec-115">Explanation</span></span>  
 <span data-ttu-id="780ec-116">このエラー/警告/情報イベントは、インターチェンジの制御番号の値 (インターチェンジ、グループ、またはトランザクション セット) が、スキーマで指定されたデータ型または正しい桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="780ec-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of a control number (interchange, group, or transaction set) in the interchange did not conform to the data type or did not have the correct number of digits specified by the schema.</span></span> <span data-ttu-id="780ec-117">スキーマは、BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema です。</span><span class="sxs-lookup"><span data-stu-id="780ec-117">The schema is the X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="780ec-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="780ec-118">User Action</span></span>  
 <span data-ttu-id="780ec-119">このエラーを解決するには、スキーマで定義されたデータ型および桁数に制御番号が準拠していることを確認してから、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="780ec-119">To resolve this error, make sure that the control number conforms to the data type and number of digits specified by the schema, and then have the interchange resent.</span></span>