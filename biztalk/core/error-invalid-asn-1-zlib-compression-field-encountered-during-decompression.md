---
title: 無効な ASN.1 ZLib 圧縮フィールドが圧縮解除処理中に発生した |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7caf047-badd-49e8-b955-554e5ec7511f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e82597f07c37633021e44cd14a8280c0d57205
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389229"
---
# <a name="invalid-asn1-zlib-compression-field-encountered-during-decompression-processing"></a><span data-ttu-id="910ee-102">圧縮解除中に無効な ASN.1 ZLib 圧縮フィールドが検出されました</span><span class="sxs-lookup"><span data-stu-id="910ee-102">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="910ee-103">詳細</span><span class="sxs-lookup"><span data-stu-id="910ee-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="910ee-104">製品名</span><span class="sxs-lookup"><span data-stu-id="910ee-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="910ee-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="910ee-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="910ee-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="910ee-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="910ee-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="910ee-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="910ee-108">EDI</span><span class="sxs-lookup"><span data-stu-id="910ee-108">EDI</span></span> |
|    <span data-ttu-id="910ee-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="910ee-109">Component</span></span>    |                                       <span data-ttu-id="910ee-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="910ee-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="910ee-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="910ee-111">Symbolic Name</span></span>  |                          <span data-ttu-id="910ee-112">InvalidOptionalZLibFieldEncountered</span><span class="sxs-lookup"><span data-stu-id="910ee-112">InvalidOptionalZLibFieldEncountered</span></span>                           |
|  <span data-ttu-id="910ee-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="910ee-113">Message Text</span></span>   |    <span data-ttu-id="910ee-114">圧縮解除中に無効な ASN.1 ZLib 圧縮フィールドが検出されました</span><span class="sxs-lookup"><span data-stu-id="910ee-114">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="910ee-115">説明</span><span class="sxs-lookup"><span data-stu-id="910ee-115">Explanation</span></span>  
 <span data-ttu-id="910ee-116">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="910ee-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="910ee-117">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="910ee-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="910ee-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="910ee-118">User Action</span></span>  
 <span data-ttu-id="910ee-119">圧縮データの構造を見直し、改ざんの形跡がないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="910ee-119">Review the structure of the compressed data and check for evidence of tampering.</span></span>