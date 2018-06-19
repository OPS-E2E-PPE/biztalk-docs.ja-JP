---
title: 無効な AS2-パーティ用に構成された名前から |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde739bd-f6f7-4e4a-8f02-9a99e9d82fc9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c370476eeccc085783c761cefb41a52eead8e208
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256978"
---
# <a name="invalid-as2-from-name-configured-for-party"></a><span data-ttu-id="18416-102">パーティに対して無効な AS2-From 名が構成されました</span><span class="sxs-lookup"><span data-stu-id="18416-102">Invalid AS2-From name configured for Party</span></span>
## <a name="details"></a><span data-ttu-id="18416-103">詳細</span><span class="sxs-lookup"><span data-stu-id="18416-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="18416-104">製品名</span><span class="sxs-lookup"><span data-stu-id="18416-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="18416-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="18416-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="18416-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="18416-106">Event ID</span></span>|-|  
|<span data-ttu-id="18416-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="18416-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="18416-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="18416-108"> EDI</span></span>|  
|<span data-ttu-id="18416-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="18416-109">Component</span></span>|<span data-ttu-id="18416-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="18416-110">AS2 Engine</span></span>|  
|<span data-ttu-id="18416-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="18416-111">Symbolic Name</span></span>|<span data-ttu-id="18416-112">InvalidAS2FromNameConfiguredError</span><span class="sxs-lookup"><span data-stu-id="18416-112">InvalidAS2FromNameConfiguredError</span></span>|  
|<span data-ttu-id="18416-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="18416-113">Message Text</span></span>|<span data-ttu-id="18416-114">無効な AS2-パーティ用に構成された名前から: {0} 値: {1}</span><span class="sxs-lookup"><span data-stu-id="18416-114">Invalid AS2-From name configured for Party: {0}   Value: {1}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="18416-115">説明</span><span class="sxs-lookup"><span data-stu-id="18416-115">Explanation</span></span>  
 <span data-ttu-id="18416-116">このエラー/警告/情報イベントは、識別されたパーティに対して構成された AS2-From ヘッダーの値が、AS2 RFC 4130 の仕様に準拠していなかったため、AS2 エンコーダーまたはデコーダーが AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="18416-116">This Error/Warning/Information event indicates that the AS2 encoder or decoder could not process the AS2 message because the value of the AS2-From header configured for the identified party did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="18416-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="18416-117">User Action</span></span>  
 <span data-ttu-id="18416-118">このエラーを解決するには、パーティに構成されている AS2-From ヘッダーが AS2 RFC 4130 のセクション 6.2 の仕様に準拠していることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="18416-118">To resolve this error, make sure that the AS2-From header configured for the party conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>