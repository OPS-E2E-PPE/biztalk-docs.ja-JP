---
title: 圧縮解除処理中に検出が無効か見つかりません ASN.1 データ OID |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 243062ae-19df-4989-b8d9-109e789f8335
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b41205b44447b447ce0ce39222e49e7b65988112
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330745"
---
# <a name="invalid-or-missing-asn1-data-oid-encountered-during-decompression-processing"></a><span data-ttu-id="fd12f-102">圧縮解除処理中に無効な ASN.1 データ OID が検出されたか、ASN.1 データ OID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="fd12f-102">Invalid or missing ASN.1 Data OID encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="fd12f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fd12f-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="fd12f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fd12f-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="fd12f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fd12f-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="fd12f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fd12f-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="fd12f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fd12f-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="fd12f-108">EDI</span><span class="sxs-lookup"><span data-stu-id="fd12f-108">EDI</span></span> |
|    <span data-ttu-id="fd12f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fd12f-109">Component</span></span>    |                                       <span data-ttu-id="fd12f-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="fd12f-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="fd12f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fd12f-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="fd12f-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fd12f-112">Message Text</span></span>   |     <span data-ttu-id="fd12f-113">圧縮解除処理中に無効な ASN.1 データ OID が検出されたか、ASN.1 データ OID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="fd12f-113">Invalid or missing ASN.1 Data OID encountered during decompression processing</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="fd12f-114">説明</span><span class="sxs-lookup"><span data-stu-id="fd12f-114">Explanation</span></span>  
 <span data-ttu-id="fd12f-115">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="fd12f-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="fd12f-116">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="fd12f-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fd12f-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fd12f-117">User Action</span></span>  
 <span data-ttu-id="fd12f-118">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd12f-118">Review the structure of the compressed data and check for tampering with the message.</span></span>