---
title: プロトコルに対するフォールバック設定が無効状態です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f14a5e46-1028-4250-af7b-8137fa927d7e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1661aed16d2a63b158f3e1ae886b7dde381da14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983443"
---
# <a name="fallback-settings-for-the-protocol-is-in-disabled-state"></a><span data-ttu-id="292c9-102">プロトコルに対するフォールバック設定が無効状態です</span><span class="sxs-lookup"><span data-stu-id="292c9-102">Fallback Settings for the Protocol is in Disabled state</span></span>
## <a name="details"></a><span data-ttu-id="292c9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="292c9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="292c9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="292c9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="292c9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="292c9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="292c9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="292c9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="292c9-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="292c9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="292c9-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="292c9-108"> EDI</span></span> |
|    <span data-ttu-id="292c9-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="292c9-109">Component</span></span>    |                                       <span data-ttu-id="292c9-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="292c9-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="292c9-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="292c9-111">Symbolic Name</span></span>  |                      <span data-ttu-id="292c9-112">AgreementResolutionFallbackSettingsDisabled</span><span class="sxs-lookup"><span data-stu-id="292c9-112">AgreementResolutionFallbackSettingsDisabled</span></span>                       |
|  <span data-ttu-id="292c9-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="292c9-113">Message Text</span></span>   |              <span data-ttu-id="292c9-114">に対するフォールバック設定が、{0}プロトコルが無効状態です。</span><span class="sxs-lookup"><span data-stu-id="292c9-114">Fallback Settings for the {0} Protocol is in Disabled state.</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="292c9-115">説明</span><span class="sxs-lookup"><span data-stu-id="292c9-115">Explanation</span></span>  
 <span data-ttu-id="292c9-116">このエラー/警告/情報イベントは、BizTalk Server がアグリーメントに解決でき、フォールバック設定にリダイレクトされたが、特定のプロトコルに対するフォールバック設定が無効な状態だったことを示します。</span><span class="sxs-lookup"><span data-stu-id="292c9-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement and has been redirected to Fallback settings and found that the fallback settings were in disabled state for the particular protocol.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="292c9-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="292c9-117">User Action</span></span>  
 <span data-ttu-id="292c9-118">このエラーを解決するのには、特定のプロトコルに対するフォールバック設定を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="292c9-118">To resolve this error, please enable the fallback settings for the particular protocol.</span></span>