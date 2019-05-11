---
title: シングル サインオン:イベント 10511 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98371982-0db5-4ae0-9f92-f05a58e23b83
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531e32a2c23c30095dc744c6e73d111ce9cccc13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400249"
---
# <a name="single-sign-on-event-10511"></a><span data-ttu-id="8cbd2-102">シングル サインオン:イベント 10511</span><span class="sxs-lookup"><span data-stu-id="8cbd2-102">Single Sign-On: Event 10511</span></span>
## <a name="details"></a><span data-ttu-id="8cbd2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8cbd2-103">Details</span></span>  

|                 |                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8cbd2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8cbd2-104">Product Name</span></span>   |                                                     <span data-ttu-id="8cbd2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8cbd2-105">Enterprise Single Sign-On</span></span>                                                     |
| <span data-ttu-id="8cbd2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8cbd2-106">Product Version</span></span> |                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                     |
|    <span data-ttu-id="8cbd2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8cbd2-107">Event ID</span></span>     |                                                               <span data-ttu-id="8cbd2-108">10511</span><span class="sxs-lookup"><span data-stu-id="8cbd2-108">10511</span></span>                                                               |
|  <span data-ttu-id="8cbd2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8cbd2-109">Event Source</span></span>   |                                                              <span data-ttu-id="8cbd2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8cbd2-110">ENTSSO</span></span>                                                               |
|    <span data-ttu-id="8cbd2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8cbd2-111">Component</span></span>    |                                                                <span data-ttu-id="8cbd2-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="8cbd2-112">N\A</span></span>                                                                |
|  <span data-ttu-id="8cbd2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8cbd2-113">Symbolic Name</span></span>  |                                                         <span data-ttu-id="8cbd2-114">SSO_ERROR_NO_DSN</span><span class="sxs-lookup"><span data-stu-id="8cbd2-114">SSO_ERROR_NO_DSN</span></span>                                                          |
|  <span data-ttu-id="8cbd2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8cbd2-115">Message Text</span></span>   | <span data-ttu-id="8cbd2-116">SQL Server および SSO データベース名がレジストリに見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-116">The SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="8cbd2-117">SSO 管理ツールを使用すると、これらの値を構成できます。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-117">Use the SSO administration tools to configure these values.</span></span> |

## <a name="explanation"></a><span data-ttu-id="8cbd2-118">説明</span><span class="sxs-lookup"><span data-stu-id="8cbd2-118">Explanation</span></span>  
 <span data-ttu-id="8cbd2-119">このエラー イベントは、SQL Server および SSO データベース名がレジストリ内に見つからなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-119">This Error event indicates that the SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="8cbd2-120">SSO サービスでは、SSO データベースに接続できるように、この情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-120">The SSO service requires this information so it can connect to the SSO database.</span></span> <span data-ttu-id="8cbd2-121">この情報は、構成中に、レジストリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-121">This information is set in the registry during configuration.</span></span> <span data-ttu-id="8cbd2-122">構成が正しく完了しませんでしたか、構成した後、レジストリ エントリが削除されたことが完了したこと可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-122">This may indicate that configuration did not complete correctly or that the registry entries have been deleted after configuration was completed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8cbd2-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8cbd2-123">User Action</span></span>  
 <span data-ttu-id="8cbd2-124">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="8cbd2-125">多くの構成の失敗を疑いがある場合は、製品の構成を解除し、構成プログラムを使用してを再構成します。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-125">If you suspect a wider configuration failure, unconfigure the product and then reconfigure using the configuration program.</span></span>  

- <span data-ttu-id="8cbd2-126">またこれら特定の不足しているレジストリ エントリは、SSO コマンド ライン ツール ssoconfig.exe SSO インストール ディレクトリの通常 C:\Program files \common files \enterprise でシングル サインオンを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-126">Alternatively these specific missing registry entries can be set using the SSO command line tool, ssoconfig.exe located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="8cbd2-127">SSO インストール ディレクトリは、異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-127">Your SSO installation directory may be different.</span></span> <span data-ttu-id="8cbd2-128">使用して、 **-setdb**必要な SQL Server および SSO データベース名を設定するオプション。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-128">Use the **-setDB** option to set the required SQL Server and SSO database names.</span></span>  

  <span data-ttu-id="8cbd2-129">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="8cbd2-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="8cbd2-130">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="8cbd2-130">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
