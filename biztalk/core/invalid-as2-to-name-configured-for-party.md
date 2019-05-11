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
ms.openlocfilehash: 3fdf3f4c307d8985df7e79ca1b8b45c569b76966
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381450"
---
# <a name="invalid-as2-to-name-configured-for-party"></a><span data-ttu-id="29f1d-102">無効な AS2-名前のパーティ用に構成するには</span><span class="sxs-lookup"><span data-stu-id="29f1d-102">Invalid AS2-To name configured for Party</span></span>
## <a name="details"></a><span data-ttu-id="29f1d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="29f1d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="29f1d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="29f1d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="29f1d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="29f1d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="29f1d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="29f1d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="29f1d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="29f1d-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="29f1d-108">EDI</span><span class="sxs-lookup"><span data-stu-id="29f1d-108">EDI</span></span> |
|    <span data-ttu-id="29f1d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="29f1d-109">Component</span></span>    |                                       <span data-ttu-id="29f1d-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="29f1d-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="29f1d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="29f1d-111">Symbolic Name</span></span>  |                            <span data-ttu-id="29f1d-112">InvalidAS2ToNameConfiguredError</span><span class="sxs-lookup"><span data-stu-id="29f1d-112">InvalidAS2ToNameConfiguredError</span></span>                             |
|  <span data-ttu-id="29f1d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="29f1d-113">Message Text</span></span>   |               <span data-ttu-id="29f1d-114">無効な AS2-名前のパーティ用に構成します。{0}   値: {1}</span><span class="sxs-lookup"><span data-stu-id="29f1d-114">Invalid AS2-To name configured for Party: {0}   Value: {1}</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="29f1d-115">説明</span><span class="sxs-lookup"><span data-stu-id="29f1d-115">Explanation</span></span>  
 <span data-ttu-id="29f1d-116">このエラー/警告/情報イベントは、AS2 エンコーダーまたはデコーダーために処理できませんでした、AS2 メッセージを示します、AS2 の値のヘッダーが AS2 RFC 4130 の仕様に準拠していなかった、識別されたパーティ用に構成します。</span><span class="sxs-lookup"><span data-stu-id="29f1d-116">This Error/Warning/Information event indicates that the AS2 encoder or decoder could not process the AS2 message because the value of the AS2-To header configured for the identified party did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29f1d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="29f1d-117">User Action</span></span>  
 <span data-ttu-id="29f1d-118">このエラーを解決することを確認、AS2 のヘッダーが AS2 RFC 4130 のセクション 6.2 の仕様に準拠しているパーティ用に構成します。</span><span class="sxs-lookup"><span data-stu-id="29f1d-118">To resolve this error, make sure that the AS2-To header configured for the party conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>