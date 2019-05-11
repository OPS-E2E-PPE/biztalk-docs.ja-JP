---
title: VersionId が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 563af6e8-f496-46c9-8b5f-7b941b2d08a5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cc840ab57b9421aabedcffbd3ae570a2553bd74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330027"
---
# <a name="invalid-versionid"></a><span data-ttu-id="af7ec-102">VersionId が無効です</span><span class="sxs-lookup"><span data-stu-id="af7ec-102">Invalid VersionId</span></span>
## <a name="details"></a><span data-ttu-id="af7ec-103">詳細</span><span class="sxs-lookup"><span data-stu-id="af7ec-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="af7ec-104">製品名</span><span class="sxs-lookup"><span data-stu-id="af7ec-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="af7ec-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="af7ec-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="af7ec-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="af7ec-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="af7ec-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="af7ec-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="af7ec-108">EDI</span><span class="sxs-lookup"><span data-stu-id="af7ec-108">EDI</span></span> |
|    <span data-ttu-id="af7ec-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="af7ec-109">Component</span></span>    |                                       <span data-ttu-id="af7ec-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="af7ec-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="af7ec-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="af7ec-111">Symbolic Name</span></span>  |                           <span data-ttu-id="af7ec-112">X12Ta1InvalidVersionIdDescription</span><span class="sxs-lookup"><span data-stu-id="af7ec-112">X12Ta1InvalidVersionIdDescription</span></span>                            |
|  <span data-ttu-id="af7ec-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="af7ec-113">Message Text</span></span>   |                                   <span data-ttu-id="af7ec-114">VersionId が無効です</span><span class="sxs-lookup"><span data-stu-id="af7ec-114">Invalid VersionId</span></span>                                    |
  
## <a name="explanation"></a><span data-ttu-id="af7ec-115">説明</span><span class="sxs-lookup"><span data-stu-id="af7ec-115">Explanation</span></span>  
 <span data-ttu-id="af7ec-116">このエラー/警告/情報イベントは、インターチェンジのバージョン識別子 (X12 インターチェンジの GS08 フィールドまたは EDIFACT インターチェンジの UNG7 フィールド) が、サービス スキーマ (BaseArtifacts.dll の X12ServiceSchema または EdifactServiceSchema) によって設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="af7ec-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the version identifier in the interchange (the GS08 field in an X12 interchange or the UNG7 field in an EDIFACT interchange) did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="af7ec-117">GS08 フィールドは、X12_AN データ型で、1 ～ 12 桁である必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7ec-117">The GS08 field must be of the X12_AN data type and between 1 and 12 digits.</span></span> <span data-ttu-id="af7ec-118">UNG7.1 のバージョンは、EDIFACT_AN データ型で、1 ～ 3 桁である必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7ec-118">The version in UNG7.1 must be of the EDIFACT_AN data type and between 1 and 3 digits.</span></span> <span data-ttu-id="af7ec-119">UNG7.2 のリリースは、EDIFACT_AN データ型で、1 ～ 3 桁である必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7ec-119">The release in UNG7.2 must be of the EDIFACT_AN data type and between 1 and 3 digits.</span></span> <span data-ttu-id="af7ec-120">UNG7.3 の関連付けの割り当てコードは、EDIFACT_AN データ型で、1 ～ 6 桁である必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7ec-120">The Association assigned code in UNG7.3 must be of the EDIFACT_AN data type and between 1 and 6 digits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="af7ec-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="af7ec-121">User Action</span></span>  
 <span data-ttu-id="af7ec-122">このエラーを解決するには、GS08 または UNG7 のバージョンがサービス スキーマで指定されたデータ型と桁数に準拠することを確認してから、インターチェンジを再度送信します。</span><span class="sxs-lookup"><span data-stu-id="af7ec-122">To resolve this error, make sure that the version in GS08 or UNG7 conforms to the data type and number of digits specified by the service schema, and then have the interchange resent.</span></span>