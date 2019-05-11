---
title: Senderid が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be8055ab-8aba-49ac-ad33-fb33d4ff3e8b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61ae69c91cc5e44d29e0f99abff9198632a02553
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381234"
---
# <a name="invalid-senderid"></a><span data-ttu-id="8006c-102">SenderId が無効です</span><span class="sxs-lookup"><span data-stu-id="8006c-102">Invalid SenderId</span></span>
## <a name="details"></a><span data-ttu-id="8006c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8006c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8006c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8006c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8006c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8006c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="8006c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8006c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="8006c-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8006c-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8006c-108">EDI</span><span class="sxs-lookup"><span data-stu-id="8006c-108">EDI</span></span> |
|    <span data-ttu-id="8006c-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8006c-109">Component</span></span>    |                                       <span data-ttu-id="8006c-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8006c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="8006c-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8006c-111">Symbolic Name</span></span>  |                            <span data-ttu-id="8006c-112">X12Ta1InvalidSenderIdDescription</span><span class="sxs-lookup"><span data-stu-id="8006c-112">X12Ta1InvalidSenderIdDescription</span></span>                            |
|  <span data-ttu-id="8006c-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8006c-113">Message Text</span></span>   |                                    <span data-ttu-id="8006c-114">SenderId が無効です</span><span class="sxs-lookup"><span data-stu-id="8006c-114">Invalid SenderId</span></span>                                    |
  
## <a name="explanation"></a><span data-ttu-id="8006c-115">説明</span><span class="sxs-lookup"><span data-stu-id="8006c-115">Explanation</span></span>  
 <span data-ttu-id="8006c-116">このエラー/警告/情報イベントは、ISA06 フィールドの送信者 ID または UNB2.1 フィールドの送信者 ID が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で確立されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8006c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Sender ID in the ISA06 field or the Sender Identification in the UNB2.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8006c-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8006c-117">User Action</span></span>  
 <span data-ttu-id="8006c-118">このエラーを解決するには、ISA06 フィールドが X12_AN データ型で、15 桁 (末尾のスペースの有無とは無関係) であるか、または UNB2.1 フィールドが EDIFACT_AN データ型で、1 ～ 35 文字の範囲であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8006c-118">To resolve this error, make sure that the ISA06 field is of the X12_AN data type and is 15 characters long (with or without trailing spaces) or that the UNB2.1 field is of the EDIFACT_AN data type and is between 1 and 35 characters.</span></span> <span data-ttu-id="8006c-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="8006c-119">Have the interchange resent.</span></span>