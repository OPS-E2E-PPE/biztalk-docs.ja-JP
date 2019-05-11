---
title: 無効なバージョンの識別子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 504b0b16-7d23-45ef-ae2a-ce1962b83f34
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 685e3229753405028104c3d2c3ad2b855640630b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330077"
---
# <a name="invalid-version-identifier"></a><span data-ttu-id="cbf35-102">バージョン識別子が無効です</span><span class="sxs-lookup"><span data-stu-id="cbf35-102">Invalid Version Identifier</span></span>
## <a name="details"></a><span data-ttu-id="cbf35-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cbf35-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="cbf35-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cbf35-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="cbf35-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cbf35-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="cbf35-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cbf35-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="cbf35-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cbf35-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="cbf35-108">EDI</span><span class="sxs-lookup"><span data-stu-id="cbf35-108">EDI</span></span> |
|    <span data-ttu-id="cbf35-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cbf35-109">Component</span></span>    |                                       <span data-ttu-id="cbf35-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="cbf35-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="cbf35-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cbf35-111">Symbolic Name</span></span>  |                       <span data-ttu-id="cbf35-112">X12Ta1InvalidVersionIdentifierDescription</span><span class="sxs-lookup"><span data-stu-id="cbf35-112">X12Ta1InvalidVersionIdentifierDescription</span></span>                        |
|  <span data-ttu-id="cbf35-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cbf35-113">Message Text</span></span>   |                               <span data-ttu-id="cbf35-114">バージョン識別子が無効です</span><span class="sxs-lookup"><span data-stu-id="cbf35-114">Invalid Version Identifier</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="cbf35-115">説明</span><span class="sxs-lookup"><span data-stu-id="cbf35-115">Explanation</span></span>  
 <span data-ttu-id="cbf35-116">このエラー/警告/情報イベントは、インターチェンジのバージョン識別子 (X12 インターチェンジの GS08 フィールドまたは EDIFACT インターチェンジの UNG7 フィールド) が、サービス スキーマ (BaseArtifacts.dll の X12ServiceSchema または EdifactServiceSchema) によって設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="cbf35-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the version identifier in the interchange (the GS08 field in an X12 interchange or the UNG7 field in an EDIFACT interchange) did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="cbf35-117">GS08 フィールドは、X12_AN データ型で、1 ～ 12 桁である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbf35-117">The GS08 field must be of the X12_AN data type and between 1 and 12 digits.</span></span> <span data-ttu-id="cbf35-118">UNG7.1 のバージョンは、EDIFACT_AN データ型で、1 ～ 3 桁である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbf35-118">The version in UNG7.1 must be of the EDIFACT_AN data type and between 1 and 3 digits.</span></span> <span data-ttu-id="cbf35-119">UNG7.2 のリリースは、EDIFACT_AN データ型で、1 ～ 3 桁である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbf35-119">The release in UNG7.2 must be of the EDIFACT_AN data type and between 1 and 3 digits.</span></span> <span data-ttu-id="cbf35-120">UNG7.3 の関連付けの割り当てコードは、EDIFACT_AN データ型で、1 ～ 6 桁である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbf35-120">The Association assigned code in UNG7.3 must be of the EDIFACT_AN data type and between 1 and 6 digits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cbf35-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cbf35-121">User Action</span></span>  
 <span data-ttu-id="cbf35-122">このエラーを解決するには、GS08 または UNG7 のバージョンがサービス スキーマで指定されたデータ型と桁数に準拠することを確認してから、インターチェンジを再度送信します。</span><span class="sxs-lookup"><span data-stu-id="cbf35-122">To resolve this error, make sure that the version in GS08 or UNG7 conforms to the data type and number of digits specified by the service schema, and then have the interchange resent.</span></span>