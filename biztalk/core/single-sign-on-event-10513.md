---
title: シングル サインオン:イベント 10513 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3306223-111f-4abf-ae65-be839b355216
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ec0cb1df806771e3676bcd580be2965498b618a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243399"
---
# <a name="single-sign-on-event-10513"></a><span data-ttu-id="d5529-102">シングル サインオン:イベント 10513</span><span class="sxs-lookup"><span data-stu-id="d5529-102">Single Sign-On: Event 10513</span></span>
## <a name="details"></a><span data-ttu-id="d5529-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d5529-103">Details</span></span>  

|                 |                                                                                      |
|-----------------|--------------------------------------------------------------------------------------|
|  <span data-ttu-id="d5529-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d5529-104">Product Name</span></span>   |                              <span data-ttu-id="d5529-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d5529-105">Enterprise Single Sign-On</span></span>                               |
| <span data-ttu-id="d5529-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d5529-106">Product Version</span></span> |              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    <span data-ttu-id="d5529-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5529-107">Event ID</span></span>     |                                        <span data-ttu-id="d5529-108">10513</span><span class="sxs-lookup"><span data-stu-id="d5529-108">10513</span></span>                                         |
|  <span data-ttu-id="d5529-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d5529-109">Event Source</span></span>   |                                        <span data-ttu-id="d5529-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d5529-110">ENTSSO</span></span>                                        |
|    <span data-ttu-id="d5529-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5529-111">Component</span></span>    |                                         <span data-ttu-id="d5529-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="d5529-112">N\A</span></span>                                          |
|  <span data-ttu-id="d5529-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d5529-113">Symbolic Name</span></span>  |                              <span data-ttu-id="d5529-114">SSO_ERROR_DB_FIRST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="d5529-114">SSO_ERROR_DB_FIRST_ACCESS</span></span>                               |
|  <span data-ttu-id="d5529-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d5529-115">Message Text</span></span>   | <span data-ttu-id="d5529-116">SSO データベースに接続に失敗しました: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="d5529-116">Failed to contact the SSO database: %1%r</span></span><br /><br /> <span data-ttu-id="d5529-117">% 2 %r</span><span class="sxs-lookup"><span data-stu-id="d5529-117">%2%r</span></span><br /><br /> <span data-ttu-id="d5529-118">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="d5529-118">Error code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="d5529-119">説明</span><span class="sxs-lookup"><span data-stu-id="d5529-119">Explanation</span></span>  
 <span data-ttu-id="d5529-120">このエラー イベントは、開始するときに、SSO サービスが、SSO データベースに接続できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="d5529-120">This Error event indicates that the SSO Service cannot connect to the SSO database when it starts.</span></span> <span data-ttu-id="d5529-121">イベント メッセージには、SQL 接続ライブラリから返されたエラー メッセージと同様に、指定した SQL Server とデータベースの名前を示すデータ ソース名 (DSN) 文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5529-121">The event message contains the Data Source Name (DSN) string indicating the specified SQL Server and database names as well as the error message that was returned from the SQL connection libraries.</span></span>  

 <span data-ttu-id="d5529-122">SSO サービスの開始時に、レジストリで指定された SQL Server および SSO データベース名を使用して SSO データベースへの接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="d5529-122">When the SSO Service starts, it will attempt to connect to the SSO database using the SQL Server and SSO database names specified in the registry.</span></span> <span data-ttu-id="d5529-123">SSO サービスでは 12 回、接続を 5 秒間、合計で 1 分の各失敗した試行を待機しているがされます。</span><span class="sxs-lookup"><span data-stu-id="d5529-123">The SSO Service will attempt to connect 12 times, waiting 5 seconds between each failed attempt, for a total of 1 minute.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d5529-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d5529-124">User Action</span></span>  
 <span data-ttu-id="d5529-125">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5529-125">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="d5529-126">SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5529-126">Verify the SQL Server (MSSQLSERVER) service is running.</span></span>  

- <span data-ttu-id="d5529-127">エラー メッセージに示されているデータ ソース名 (DSN) 文字列が正しいと適切な SQL Server とデータベース名を確認します。</span><span class="sxs-lookup"><span data-stu-id="d5529-127">Verify the Data Source Name (DSN) string indicated in the error message is correct and contains the correct SQL Server and database names.</span></span>  

  <span data-ttu-id="d5529-128">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="d5529-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="d5529-129">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="d5529-129">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  

- [<span data-ttu-id="d5529-130">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="d5529-130">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  

- [<span data-ttu-id="d5529-131">SSO の構成</span><span class="sxs-lookup"><span data-stu-id="d5529-131">Configuring SSO</span></span>](../core/configuring-sso.md)  

- <span data-ttu-id="d5529-132">SQL Server オンライン ブック</span><span class="sxs-lookup"><span data-stu-id="d5529-132">SQL Server Books Online</span></span>
