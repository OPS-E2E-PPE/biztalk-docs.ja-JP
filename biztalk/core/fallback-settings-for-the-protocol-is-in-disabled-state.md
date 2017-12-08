---
title: "プロトコルに対するフォールバック設定が無効状態です |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f14a5e46-1028-4250-af7b-8137fa927d7e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9060dbe2bf3644310d862d4949d2cf944269105d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fallback-settings-for-the-protocol-is-in-disabled-state"></a><span data-ttu-id="8185e-102">プロトコルに対するフォールバック設定が無効状態です</span><span class="sxs-lookup"><span data-stu-id="8185e-102">Fallback Settings for the Protocol is in Disabled state</span></span>
## <a name="details"></a><span data-ttu-id="8185e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8185e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8185e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8185e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8185e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8185e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="8185e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8185e-106">Event ID</span></span>|-|  
|<span data-ttu-id="8185e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8185e-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8185e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="8185e-108"> EDI</span></span>|  
|<span data-ttu-id="8185e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8185e-109">Component</span></span>|<span data-ttu-id="8185e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8185e-110">EDI Engine</span></span>|  
|<span data-ttu-id="8185e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8185e-111">Symbolic Name</span></span>|<span data-ttu-id="8185e-112">AgreementResolutionFallbackSettingsDisabled</span><span class="sxs-lookup"><span data-stu-id="8185e-112">AgreementResolutionFallbackSettingsDisabled</span></span>|  
|<span data-ttu-id="8185e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8185e-113">Message Text</span></span>|<span data-ttu-id="8185e-114">{0} プロトコルに対するフォールバック設定が無効状態です。</span><span class="sxs-lookup"><span data-stu-id="8185e-114">Fallback Settings for the {0} Protocol is in Disabled state.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8185e-115">説明</span><span class="sxs-lookup"><span data-stu-id="8185e-115">Explanation</span></span>  
 <span data-ttu-id="8185e-116">このエラー/警告/情報イベントは、BizTalk Server がアグリーメントに解決でき、フォールバック設定にリダイレクトされたが、特定のプロトコルに対するフォールバック設定が無効な状態だったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8185e-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement and has been redirected to Fallback settings and found that the fallback settings were in disabled state for the particular protocol.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8185e-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8185e-117">User Action</span></span>  
 <span data-ttu-id="8185e-118">このエラーを解決するのには、特定のプロトコルに対するフォールバック設定を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="8185e-118">To resolve this error, please enable the fallback settings for the particular protocol.</span></span>