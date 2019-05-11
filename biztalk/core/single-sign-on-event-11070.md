---
title: シングル サインオン:イベント 11070 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb669df9-710a-4792-bdd4-cca0c03fcda2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1382d436528f630ec4abb51af98599371d69a297
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243518"
---
# <a name="single-sign-on-event-11070"></a><span data-ttu-id="58dbb-102">シングル サインオン:イベント 11070</span><span class="sxs-lookup"><span data-stu-id="58dbb-102">Single Sign-On: Event 11070</span></span>
## <a name="details"></a><span data-ttu-id="58dbb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="58dbb-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="58dbb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="58dbb-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="58dbb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="58dbb-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="58dbb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="58dbb-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="58dbb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="58dbb-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="58dbb-108">11070</span><span class="sxs-lookup"><span data-stu-id="58dbb-108">11070</span></span>                                                                                                         |
|  <span data-ttu-id="58dbb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="58dbb-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="58dbb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="58dbb-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="58dbb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="58dbb-111">Component</span></span>    |                                                                                                          <span data-ttu-id="58dbb-112">なし</span><span class="sxs-lookup"><span data-stu-id="58dbb-112">N/A</span></span>                                                                                                          |
|  <span data-ttu-id="58dbb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="58dbb-113">Symbolic Name</span></span>  |                                                                                             <span data-ttu-id="58dbb-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="58dbb-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span></span>                                                                                              |
|  <span data-ttu-id="58dbb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="58dbb-115">Message Text</span></span>   | <span data-ttu-id="58dbb-116">現在、この SSO サーバーでは、MIIS からの Windows パスワード変更ができないように構成されています。</span><span class="sxs-lookup"><span data-stu-id="58dbb-116">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span> <span data-ttu-id="58dbb-117">'ssoconfig -allowPS MIIS yes' または SSO 管理 MMC を使用してください。%r</span><span class="sxs-lookup"><span data-stu-id="58dbb-117">Use 'ssoconfig -allowPS MIIS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="58dbb-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="58dbb-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="58dbb-119">クライアント ユーザー: %2</span><span class="sxs-lookup"><span data-stu-id="58dbb-119">Client User: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="58dbb-120">説明</span><span class="sxs-lookup"><span data-stu-id="58dbb-120">Explanation</span></span>  
 <span data-ttu-id="58dbb-121">現在、この SSO サーバーでは、MIIS からの Windows パスワード変更ができないように構成されています。</span><span class="sxs-lookup"><span data-stu-id="58dbb-121">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="58dbb-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="58dbb-122">User Action</span></span>  
 <span data-ttu-id="58dbb-123">MIIS からの Windows パスワードの変更を許可する、**サーバー スナップイン**、**パスワード同期プロパティ**] タブで [ **MIIS からパスワード同期を許可します。**</span><span class="sxs-lookup"><span data-stu-id="58dbb-123">To allow Windows password changes from MIIS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from MIIS.**</span></span>  
  
 <span data-ttu-id="58dbb-124">詳細については、次を参照してください。[サーバー スナップインを使用する](../core/how-to-use-the-servers-snap-in.md)します。</span><span class="sxs-lookup"><span data-stu-id="58dbb-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>