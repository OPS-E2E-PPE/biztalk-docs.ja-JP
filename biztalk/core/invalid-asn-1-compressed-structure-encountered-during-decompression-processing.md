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
ms.openlocfilehash: 1d545b1b2418546bc27adb89674a57d9c915d0e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381393"
---
# <a name="invalid-asn1-compressed-structure-encountered-during-decompression-processing"></a><span data-ttu-id="9f919-102">無効な ASN.1 圧縮構造の圧縮解除処理中に発生しました。</span><span class="sxs-lookup"><span data-stu-id="9f919-102">Invalid ASN.1 compressed structure encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="9f919-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9f919-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9f919-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9f919-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9f919-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9f919-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9f919-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9f919-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9f919-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9f919-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9f919-108">EDI</span><span class="sxs-lookup"><span data-stu-id="9f919-108">EDI</span></span> |
|    <span data-ttu-id="9f919-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9f919-109">Component</span></span>    |                                       <span data-ttu-id="9f919-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="9f919-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="9f919-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9f919-111">Symbolic Name</span></span>  |                       <span data-ttu-id="9f919-112">InvalidASN1CompressedStructureEncountered</span><span class="sxs-lookup"><span data-stu-id="9f919-112">InvalidASN1CompressedStructureEncountered</span></span>                        |
|  <span data-ttu-id="9f919-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9f919-113">Message Text</span></span>   | <span data-ttu-id="9f919-114">圧縮解除処理中に無効な ASN.1 圧縮ヘッダーが検出されたか、ASN.1 圧縮ヘッダーが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="9f919-114">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9f919-115">説明</span><span class="sxs-lookup"><span data-stu-id="9f919-115">Explanation</span></span>  
 <span data-ttu-id="9f919-116">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="9f919-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="9f919-117">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9f919-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f919-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9f919-118">User Action</span></span>  
 <span data-ttu-id="9f919-119">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f919-119">Review the structure of the compressed data and check for tampering with the message.</span></span>