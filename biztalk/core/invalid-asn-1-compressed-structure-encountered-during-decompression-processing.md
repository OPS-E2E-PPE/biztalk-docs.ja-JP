---
title: 無効な ASN.1 圧縮構造の圧縮解除処理中に発生した |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e5ebbd6-249a-4746-8ee6-cfb1f52ecc94
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07d1e44e38665a6a643131545afb660945a9f07e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969075"
---
# <a name="invalid-asn1-compressed-structure-encountered-during-decompression-processing"></a><span data-ttu-id="9862b-102">圧縮解除処理中に無効な ASN.1 圧縮構造が検出されました</span><span class="sxs-lookup"><span data-stu-id="9862b-102">Invalid ASN.1 compressed structure encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="9862b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9862b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9862b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9862b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9862b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9862b-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9862b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9862b-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9862b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9862b-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9862b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9862b-108"> EDI</span></span> |
|    <span data-ttu-id="9862b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9862b-109">Component</span></span>    |                                       <span data-ttu-id="9862b-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="9862b-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="9862b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9862b-111">Symbolic Name</span></span>  |                       <span data-ttu-id="9862b-112">InvalidASN1CompressedStructureEncountered</span><span class="sxs-lookup"><span data-stu-id="9862b-112">InvalidASN1CompressedStructureEncountered</span></span>                        |
|  <span data-ttu-id="9862b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9862b-113">Message Text</span></span>   | <span data-ttu-id="9862b-114">圧縮解除処理中に無効な ASN.1 圧縮ヘッダーが検出されたか、ASN.1 圧縮ヘッダーが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="9862b-114">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9862b-115">説明</span><span class="sxs-lookup"><span data-stu-id="9862b-115">Explanation</span></span>  
 <span data-ttu-id="9862b-116">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="9862b-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="9862b-117">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9862b-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9862b-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9862b-118">User Action</span></span>  
 <span data-ttu-id="9862b-119">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9862b-119">Review the structure of the compressed data and check for tampering with the message.</span></span>