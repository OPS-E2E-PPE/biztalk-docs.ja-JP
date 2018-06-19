---
title: 'シングル サインオン: イベント 11029 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd7cb5b0-532c-4f50-849d-4d1644026463
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5f24cee6fcbe7db5ce0b4f31d458a5a29118c3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277194"
---
# <a name="single-sign-on-event-11029"></a><span data-ttu-id="874f1-102">シングル サインオン: イベント 11029</span><span class="sxs-lookup"><span data-stu-id="874f1-102">Single Sign-On: Event 11029</span></span>
## <a name="details"></a><span data-ttu-id="874f1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="874f1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="874f1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="874f1-104">Product Name</span></span>|<span data-ttu-id="874f1-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="874f1-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="874f1-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="874f1-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="874f1-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="874f1-107">Event ID</span></span>|<span data-ttu-id="874f1-108">11029</span><span class="sxs-lookup"><span data-stu-id="874f1-108">11029</span></span>|  
|<span data-ttu-id="874f1-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="874f1-109">Event Source</span></span>|<span data-ttu-id="874f1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="874f1-110">ENTSSO</span></span>|  
|<span data-ttu-id="874f1-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="874f1-111">Component</span></span>|<span data-ttu-id="874f1-112">なし</span><span class="sxs-lookup"><span data-stu-id="874f1-112">N/A</span></span>|  
|<span data-ttu-id="874f1-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="874f1-113">Symbolic Name</span></span>|<span data-ttu-id="874f1-114">SSO_INFO_CASE_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="874f1-114">SSO_INFO_CASE_SENSITIVE</span></span>|  
|<span data-ttu-id="874f1-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="874f1-115">Message Text</span></span>|<span data-ttu-id="874f1-116">SSO データベースでは、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="874f1-116">The SSO database is case sensitive.</span></span> <span data-ttu-id="874f1-117">SSO サーバーは大文字と小文字を区別するモードで実行します。</span><span class="sxs-lookup"><span data-stu-id="874f1-117">The SSO server will run in case sensitive mode.</span></span> <span data-ttu-id="874f1-118">Details.%r のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="874f1-118">See documentation for details.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="874f1-119">説明</span><span class="sxs-lookup"><span data-stu-id="874f1-119">Explanation</span></span>  
 <span data-ttu-id="874f1-120">既定では、SSO サーバーでは大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="874f1-120">By default the SSO server is not case-sensitive.</span></span> <span data-ttu-id="874f1-121">ただし、SQL Server SSO データベースが大文字と小文字を区別するように構成されているので、SSO サーバーも大文字と小文字を区別するモードで実行します。</span><span class="sxs-lookup"><span data-stu-id="874f1-121">However, the SQL Server SSO database has been configured to be case-sensitive, so the SSO Server will also run in case sensitive mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="874f1-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="874f1-122">User Action</span></span>  
 <span data-ttu-id="874f1-123">アプリケーション名および外部アカウント名は大文字と小文字が区別されるようになっているので、これらを指定するときはそのことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="874f1-123">Be aware of this when specifying application names and external account names as they are now case-sensitive.</span></span> <span data-ttu-id="874f1-124">詳細については、次を参照してください。 [SSO サーバー](../core/sso-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="874f1-124">For more information, see [SSO Server](../core/sso-server.md).</span></span>