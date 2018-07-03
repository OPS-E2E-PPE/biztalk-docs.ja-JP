---
title: 'シングル サインオン: イベント 10511 |Microsoft Docs'
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
ms.openlocfilehash: 828dab394e773f99b31ca23f19b2816ab8558a10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992091"
---
# <a name="single-sign-on-event-10511"></a><span data-ttu-id="7ab74-102">シングル サインオン: イベント 10511</span><span class="sxs-lookup"><span data-stu-id="7ab74-102">Single Sign-On: Event 10511</span></span>
## <a name="details"></a><span data-ttu-id="7ab74-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7ab74-103">Details</span></span>  

|                 |                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7ab74-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7ab74-104">Product Name</span></span>   |                                                     <span data-ttu-id="7ab74-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7ab74-105">Enterprise Single Sign-On</span></span>                                                     |
| <span data-ttu-id="7ab74-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7ab74-106">Product Version</span></span> |                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                     |
|    <span data-ttu-id="7ab74-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7ab74-107">Event ID</span></span>     |                                                               <span data-ttu-id="7ab74-108">10511</span><span class="sxs-lookup"><span data-stu-id="7ab74-108">10511</span></span>                                                               |
|  <span data-ttu-id="7ab74-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7ab74-109">Event Source</span></span>   |                                                              <span data-ttu-id="7ab74-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7ab74-110">ENTSSO</span></span>                                                               |
|    <span data-ttu-id="7ab74-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7ab74-111">Component</span></span>    |                                                                <span data-ttu-id="7ab74-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7ab74-112">N\A</span></span>                                                                |
|  <span data-ttu-id="7ab74-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7ab74-113">Symbolic Name</span></span>  |                                                         <span data-ttu-id="7ab74-114">SSO_ERROR_NO_DSN</span><span class="sxs-lookup"><span data-stu-id="7ab74-114">SSO_ERROR_NO_DSN</span></span>                                                          |
|  <span data-ttu-id="7ab74-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7ab74-115">Message Text</span></span>   | <span data-ttu-id="7ab74-116">SQL Server 名と SSO データベース名がレジストリ内に見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ab74-116">The SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="7ab74-117">SSO 管理ツールを使用してこれらの値を構成してください。</span><span class="sxs-lookup"><span data-stu-id="7ab74-117">Use the SSO administration tools to configure these values.</span></span> |

## <a name="explanation"></a><span data-ttu-id="7ab74-118">説明</span><span class="sxs-lookup"><span data-stu-id="7ab74-118">Explanation</span></span>  
 <span data-ttu-id="7ab74-119">このエラー イベントは、SQL Server 名と SSO データベース名がレジストリ内に見つからなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="7ab74-119">This Error event indicates that the SQL Server and SSO database names were not found in the registry.</span></span> <span data-ttu-id="7ab74-120">SSO サービスでは、SSO データベースに接続するためにこの情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="7ab74-120">The SSO service requires this information so it can connect to the SSO database.</span></span> <span data-ttu-id="7ab74-121">この情報は、構成中にレジストリ内で設定されます。</span><span class="sxs-lookup"><span data-stu-id="7ab74-121">This information is set in the registry during configuration.</span></span> <span data-ttu-id="7ab74-122">このエラーは、構成が正常に完了していないか、または構成の完了後にレジストリ エントリが削除されたことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ab74-122">This may indicate that configuration did not complete correctly or that the registry entries have been deleted after configuration was completed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7ab74-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7ab74-123">User Action</span></span>  
 <span data-ttu-id="7ab74-124">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7ab74-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="7ab74-125">広い範囲での構成の失敗が疑われる場合は、製品の構成を解除し、構成プログラムを使用して再構成します。</span><span class="sxs-lookup"><span data-stu-id="7ab74-125">If you suspect a wider configuration failure, unconfigure the product and then reconfigure using the configuration program.</span></span>  

- <span data-ttu-id="7ab74-126">この代わりに、これらの存在しない特定のレジストリ エントリを、SSO コマンド ライン ツール ssoconfig.exe を使用して設定することもできます。ssoconfig.exe は、SSO インストール ディレクトリ (通常、C:\Program Files\Common Files\Enterprise Single Sign-On) にあります。</span><span class="sxs-lookup"><span data-stu-id="7ab74-126">Alternatively these specific missing registry entries can be set using the SSO command line tool, ssoconfig.exe located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="7ab74-127">SSO インストール ディレクトリが違う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ab74-127">Your SSO installation directory may be different.</span></span> <span data-ttu-id="7ab74-128">使用して、 **-setdb**必要な SQL Server および SSO データベース名を設定するオプション。</span><span class="sxs-lookup"><span data-stu-id="7ab74-128">Use the **-setDB** option to set the required SQL Server and SSO database names.</span></span>  

  <span data-ttu-id="7ab74-129">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="7ab74-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="7ab74-130">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="7ab74-130">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
