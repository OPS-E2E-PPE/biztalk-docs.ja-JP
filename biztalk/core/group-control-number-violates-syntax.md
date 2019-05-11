---
title: グループ制御番号が構文に違反しています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e173c914-cb5c-4369-ac2f-8f9abee420cb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7664a85d0cb1bb0c83ef53c6c584c51b532d6c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344880"
---
# <a name="group-control-number-violates-syntax"></a><span data-ttu-id="5c70d-102">グループ制御番号が構文に違反しています</span><span class="sxs-lookup"><span data-stu-id="5c70d-102">Group control number violates syntax</span></span>
## <a name="details"></a><span data-ttu-id="5c70d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5c70d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5c70d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5c70d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5c70d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5c70d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5c70d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5c70d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5c70d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5c70d-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5c70d-108">EDI</span><span class="sxs-lookup"><span data-stu-id="5c70d-108">EDI</span></span> |
|    <span data-ttu-id="5c70d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5c70d-109">Component</span></span>    |                                       <span data-ttu-id="5c70d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="5c70d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="5c70d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5c70d-111">Symbolic Name</span></span>  |                          <span data-ttu-id="5c70d-112">X12FaInvalidControlNumberDescription</span><span class="sxs-lookup"><span data-stu-id="5c70d-112">X12FaInvalidControlNumberDescription</span></span>                          |
|  <span data-ttu-id="5c70d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5c70d-113">Message Text</span></span>   |                          <span data-ttu-id="5c70d-114">グループ制御番号が構文に違反しています</span><span class="sxs-lookup"><span data-stu-id="5c70d-114">Group control number violates syntax</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="5c70d-115">説明</span><span class="sxs-lookup"><span data-stu-id="5c70d-115">Explanation</span></span>  
 <span data-ttu-id="5c70d-116">このエラー/警告/情報イベントは、インターチェンジの GS06 および GE02 フィールドのグループ制御番号が、サービス スキーマで指定されたデータ型または長さに準拠していなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5c70d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the group control number in the GS06 and GE02 fields of the interchange did not conform to the data type or length specified in the service schema.</span></span> <span data-ttu-id="5c70d-117">サービス スキーマは BaseArtifacts.dll 内の X12ServiceSchema です。</span><span class="sxs-lookup"><span data-stu-id="5c70d-117">The service schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5c70d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5c70d-118">User Action</span></span>  
 <span data-ttu-id="5c70d-119">このエラーを解決するには、インターチェンジの GS06 および GE02 フィールドに含まれているグループ制御番号が、サービス スキーマに指定されているデータ型 (X12_N0) および長さ (1 ～ 9 桁) に準拠していることを確認して、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="5c70d-119">To resolve this error, make sure that the group control numbers contained in the GS06 and GE02 fields of the interchange conform to the data type (X12_N0) and length (between one and nine digits) specified in the service schema, and then have the interchange resent.</span></span>