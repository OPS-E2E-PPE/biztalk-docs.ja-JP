---
title: 圧縮解除処理中に検出が無効か見つかりません ASN.1 ZLib OID |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb41e0fe-2fdd-4dfc-830f-c28dfe6efac8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a3634fc02958c47bb933a100e60214de3082ea2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381335"
---
# <a name="invalid-or-missing-asn1-zlib-oid-encountered-during-decompression-processing"></a><span data-ttu-id="a8330-102">圧縮解除処理中に無効な ASN.1 ZLib データ OID が検出されたか、ASN.1 ZLib データ OID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="a8330-102">Invalid or missing ASN.1 ZLib OID encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="a8330-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a8330-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a8330-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a8330-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a8330-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a8330-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a8330-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a8330-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a8330-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a8330-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a8330-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a8330-108">EDI</span></span> |
|    <span data-ttu-id="a8330-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a8330-109">Component</span></span>    |                                       <span data-ttu-id="a8330-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="a8330-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="a8330-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a8330-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="a8330-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a8330-112">Message Text</span></span>   |     <span data-ttu-id="a8330-113">圧縮解除処理中に無効な ASN.1 ZLib データ OID が検出されたか、ASN.1 ZLib データ OID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="a8330-113">Invalid or missing ASN.1 ZLib OID encountered during decompression processing</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="a8330-114">説明</span><span class="sxs-lookup"><span data-stu-id="a8330-114">Explanation</span></span>  
 <span data-ttu-id="a8330-115">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="a8330-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="a8330-116">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a8330-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8330-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a8330-117">User Action</span></span>  
 <span data-ttu-id="a8330-118">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8330-118">Review the structure of the compressed data and check for tampering with the message.</span></span>