---
title: 見つかりませんプロトコルに対するフォールバック設定 |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d93e5db1-16a3-4796-8fa2-fef934508034
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5b3f8ea35f4f29859f5156ff254137ea7a8f8db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245906"
---
# <a name="fallback-settings-for-the-protocol-not-found"></a><span data-ttu-id="32b53-102">プロトコルに対するフォールバック設定が見つかりません</span><span class="sxs-lookup"><span data-stu-id="32b53-102">Fallback Settings for the Protocol not found</span></span>
## <a name="details"></a><span data-ttu-id="32b53-103">詳細</span><span class="sxs-lookup"><span data-stu-id="32b53-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32b53-104">製品名</span><span class="sxs-lookup"><span data-stu-id="32b53-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="32b53-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="32b53-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="32b53-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="32b53-106">Event ID</span></span>|-|  
|<span data-ttu-id="32b53-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="32b53-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="32b53-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="32b53-108"> EDI</span></span>|  
|<span data-ttu-id="32b53-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="32b53-109">Component</span></span>|<span data-ttu-id="32b53-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="32b53-110">EDI Engine</span></span>|  
|<span data-ttu-id="32b53-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="32b53-111">Symbolic Name</span></span>|<span data-ttu-id="32b53-112">AgreementResolutionFallbackSettingsNotFound</span><span class="sxs-lookup"><span data-stu-id="32b53-112">AgreementResolutionFallbackSettingsNotFound</span></span>|  
|<span data-ttu-id="32b53-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="32b53-113">Message Text</span></span>|<span data-ttu-id="32b53-114">{0} プロトコルに対するフォールバック設定が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="32b53-114">Fallback Settings for the {0} Protocol not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="32b53-115">説明</span><span class="sxs-lookup"><span data-stu-id="32b53-115">Explanation</span></span>  
 <span data-ttu-id="32b53-116">このエラー/警告/情報イベントは、BizTalk Server がアグリーメントに解決でき、フォールバック設定にリダイレクトされたが、特定のプロトコルに対するフォールバック設定がなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="32b53-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement and has been redirected to Fallback settings and found that the fallback settings were not there for the particular protocol.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32b53-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="32b53-117">User Action</span></span>  
 <span data-ttu-id="32b53-118">このエラーを解決するには、特定のプロトコルのフォールバック設定を構成してください。</span><span class="sxs-lookup"><span data-stu-id="32b53-118">To resolve this error, please configure the fallback settings for the particular protocol.</span></span>