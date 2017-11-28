---
title: "無効な AS2-パーティ用に構成名 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a203e5f2-d1d9-433f-b2bb-d679bb8fea58
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c06adc5a459f7dfd05508312494555fb2651114
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-to-name-configured-for-party"></a><span data-ttu-id="635d0-102">パーティに対して無効な AS2-To 名が構成されました</span><span class="sxs-lookup"><span data-stu-id="635d0-102">Invalid AS2-To name configured for Party</span></span>
## <a name="details"></a><span data-ttu-id="635d0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="635d0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="635d0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="635d0-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="635d0-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="635d0-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="635d0-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="635d0-106">Event ID</span></span>|-|  
|<span data-ttu-id="635d0-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="635d0-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="635d0-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="635d0-108"> EDI</span></span>|  
|<span data-ttu-id="635d0-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="635d0-109">Component</span></span>|<span data-ttu-id="635d0-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="635d0-110">AS2 Engine</span></span>|  
|<span data-ttu-id="635d0-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="635d0-111">Symbolic Name</span></span>|<span data-ttu-id="635d0-112">InvalidAS2ToNameConfiguredError</span><span class="sxs-lookup"><span data-stu-id="635d0-112">InvalidAS2ToNameConfiguredError</span></span>|  
|<span data-ttu-id="635d0-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="635d0-113">Message Text</span></span>|<span data-ttu-id="635d0-114">無効な AS2-名前のパーティに構成する: {0} 値: {1}</span><span class="sxs-lookup"><span data-stu-id="635d0-114">Invalid AS2-To name configured for Party: {0}   Value: {1}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="635d0-115">説明</span><span class="sxs-lookup"><span data-stu-id="635d0-115">Explanation</span></span>  
 <span data-ttu-id="635d0-116">このエラー/警告/情報イベントは、識別されたパーティに対して構成された AS2-To ヘッダーの値が、AS2 RFC 4130 の仕様に準拠していなかったため、AS2 エンコーダーまたはデコーダーが AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="635d0-116">This Error/Warning/Information event indicates that the AS2 encoder or decoder could not process the AS2 message because the value of the AS2-To header configured for the identified party did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="635d0-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="635d0-117">User Action</span></span>  
 <span data-ttu-id="635d0-118">このエラーを解決するには、パーティに対して構成された AS2-To ヘッダーが、AS2 RFC 4130 のセクション 6.2 の仕様に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="635d0-118">To resolve this error, make sure that the AS2-To header configured for the party conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>