---
title: 受信者 id を使用してアクセス契約にできませんでした |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbdd869e244f3d59ebd267d492112a1e29441c2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258493"
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a><span data-ttu-id="3a782-102">受信者 id を使用してアグリーメントにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="3a782-102">Unable to access agreement using receiver identity</span></span>
## <a name="details"></a><span data-ttu-id="3a782-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3a782-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="3a782-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3a782-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3a782-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3a782-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="3a782-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3a782-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="3a782-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3a782-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3a782-108">EDI</span><span class="sxs-lookup"><span data-stu-id="3a782-108">EDI</span></span> |
|    <span data-ttu-id="3a782-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3a782-109">Component</span></span>    |                                       <span data-ttu-id="3a782-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="3a782-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="3a782-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3a782-111">Symbolic Name</span></span>  |                         <span data-ttu-id="3a782-112">UnableToLocateAS2PartyByPartyNameError</span><span class="sxs-lookup"><span data-stu-id="3a782-112">UnableToLocateAS2PartyByPartyNameError</span></span>                         |
|  <span data-ttu-id="3a782-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3a782-113">Message Text</span></span>   |                <span data-ttu-id="3a782-114">受信者 id を使用してアクセス契約を読み込めません。 {0}</span><span class="sxs-lookup"><span data-stu-id="3a782-114">Unable to access agreement using receiver identity: {0}</span></span>                 |
  
## <a name="explanation"></a><span data-ttu-id="3a782-115">説明</span><span class="sxs-lookup"><span data-stu-id="3a782-115">Explanation</span></span>  
 <span data-ttu-id="3a782-116">このエラーを示すこと、送信パイプラインを特定できませんでした、送信 AS2 メッセージのパーティ、送信メッセージの AS2To コンテキスト プロパティまたは Http.UserHttpHeaders コンテキスト プロパティの名前で、AS2To プロパティも一致しないため、AS2 パーティ-AS2 メッセージの受信者] ページ、[AS2 のプロパティ] ダイアログ ボックスの [パーティのプロパティにします。</span><span class="sxs-lookup"><span data-stu-id="3a782-116">This error indicates that the send pipeline could not determine the party for an outgoing AS2 message because it could not match the AS2To context property of the outbound message or the AS2To property in the Http.UserHttpHeaders context property with the name of the party in the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3a782-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3a782-117">User Action</span></span>  
 <span data-ttu-id="3a782-118">このエラーを解決するには、設定、AS2 のエラーでは、AS2 メッセージに関連付けられている適切なパーティ名を AS2 のプロパティ ダイアログ ボックスのページを AS2 メッセージの受信者としてのパーティのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3a782-118">To resolve this error, set the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box to the appropriate party name associated with the AS2 message that is in error.</span></span>