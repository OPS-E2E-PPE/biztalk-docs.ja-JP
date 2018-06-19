---
title: 無効または見つからない ASN.1 圧縮データ OID 圧縮解除処理中に発生した |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0171daa8-289a-43f1-8cbf-d779ef9dc2ea
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05af1fc0c9f6516f180cf629cd0a21d838f0b4f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241754"
---
# <a name="invalid-or-missing-asn1-compressed-data-oid-encountered-during-decompression-processing"></a><span data-ttu-id="f5f07-102">圧縮解除処理中に無効な ASN.1 圧縮データ OID が検出されたか、ASN.1 圧縮データ OID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="f5f07-102">Invalid or missing ASN.1 Compressed Data OID encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="f5f07-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f5f07-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5f07-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f5f07-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f5f07-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f5f07-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f5f07-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f5f07-106">Event ID</span></span>|-|  
|<span data-ttu-id="f5f07-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f5f07-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f5f07-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f5f07-108"> EDI</span></span>|  
|<span data-ttu-id="f5f07-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f5f07-109">Component</span></span>|<span data-ttu-id="f5f07-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="f5f07-110">AS2 Engine</span></span>|  
|<span data-ttu-id="f5f07-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f5f07-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="f5f07-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f5f07-112">Message Text</span></span>|<span data-ttu-id="f5f07-113">圧縮解除処理中に無効な ASN.1 圧縮データ OID が検出されたか、ASN.1 圧縮データ OID が見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="f5f07-113">Invalid or missing ASN.1 Compressed Data OID encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f5f07-114">説明</span><span class="sxs-lookup"><span data-stu-id="f5f07-114">Explanation</span></span>  
 <span data-ttu-id="f5f07-115">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="f5f07-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="f5f07-116">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f5f07-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f5f07-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f5f07-117">User Action</span></span>  
 <span data-ttu-id="f5f07-118">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5f07-118">Review the structure of the compressed data and check for tampering with the message.</span></span>