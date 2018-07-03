---
title: 無効な AS2 の名前がパーティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a203e5f2-d1d9-433f-b2bb-d679bb8fea58
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84b97fc20ec6280557fdd050b25b17e2e068fc08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970667"
---
# <a name="invalid-as2-to-name-configured-for-party"></a><span data-ttu-id="91a31-102">パーティに対して無効な AS2-To 名が構成されました</span><span class="sxs-lookup"><span data-stu-id="91a31-102">Invalid AS2-To name configured for Party</span></span>
## <a name="details"></a><span data-ttu-id="91a31-103">詳細</span><span class="sxs-lookup"><span data-stu-id="91a31-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="91a31-104">製品名</span><span class="sxs-lookup"><span data-stu-id="91a31-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="91a31-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="91a31-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="91a31-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="91a31-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="91a31-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="91a31-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="91a31-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="91a31-108"> EDI</span></span> |
|    <span data-ttu-id="91a31-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="91a31-109">Component</span></span>    |                                       <span data-ttu-id="91a31-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="91a31-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="91a31-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="91a31-111">Symbolic Name</span></span>  |                            <span data-ttu-id="91a31-112">InvalidAS2ToNameConfiguredError</span><span class="sxs-lookup"><span data-stu-id="91a31-112">InvalidAS2ToNameConfiguredError</span></span>                             |
|  <span data-ttu-id="91a31-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="91a31-113">Message Text</span></span>   |               <span data-ttu-id="91a31-114">無効な AS2-名前のパーティ用に構成する:{0}値。 {1}</span><span class="sxs-lookup"><span data-stu-id="91a31-114">Invalid AS2-To name configured for Party: {0}   Value: {1}</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="91a31-115">説明</span><span class="sxs-lookup"><span data-stu-id="91a31-115">Explanation</span></span>  
 <span data-ttu-id="91a31-116">このエラー/警告/情報イベントは、識別されたパーティに対して構成された AS2-To ヘッダーの値が、AS2 RFC 4130 の仕様に準拠していなかったため、AS2 エンコーダーまたはデコーダーが AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="91a31-116">This Error/Warning/Information event indicates that the AS2 encoder or decoder could not process the AS2 message because the value of the AS2-To header configured for the identified party did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="91a31-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="91a31-117">User Action</span></span>  
 <span data-ttu-id="91a31-118">このエラーを解決するには、パーティに対して構成された AS2-To ヘッダーが、AS2 RFC 4130 のセクション 6.2 の仕様に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="91a31-118">To resolve this error, make sure that the AS2-To header configured for the party conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>