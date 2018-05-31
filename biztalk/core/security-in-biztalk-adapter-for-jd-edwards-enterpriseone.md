---
title: SSO を使用して JD Edwards EnterpriseOne を保護する |Microsoft ドキュメント
description: BizTalk Server で Microsoft BizTalk Adapter JD Edwards EnterpriseOne を使用する場合のセキュリティの概要
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24c9802e-485d-4632-bc27-3285f35d34e3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb669cc197fba3322a1c1736004aa0fd57b942d3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013073"
---
# <a name="security-in-jd-edwards-enterpriseone"></a><span data-ttu-id="53abf-103">JD Edwards EnterpriseOne のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="53abf-103">Security in JD Edwards EnterpriseOne</span></span>

## <a name="overview"></a><span data-ttu-id="53abf-104">概要</span><span class="sxs-lookup"><span data-stu-id="53abf-104">Overview</span></span>

<span data-ttu-id="53abf-105">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne は、シングル サインオン (SSO) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="53abf-105">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="53abf-106">エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、JD Edwards EnterpriseOne などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="53abf-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as JD Edwards EnterpriseOne.</span></span> 

<span data-ttu-id="53abf-107">このセクションでは、セキュリティで保護された環境で Microsoft BizTalk Server Adapter for JD Edwards EnterpriseOne を展開するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="53abf-107">This section provides guidelines for deploying Microsoft BizTalk Server Adapter for JD Edwards EnterpriseOne in a secure environment.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="53abf-108">承認されたユーザーだけに、BizTalk adapter for JD Edwards EnterpriseOne の使用を制限することをお勧めように、クライアント ファイルが基幹業務アプリケーションに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="53abf-108">We recommended that you restrict the use of BizTalk Adapter for JD Edwards EnterpriseOne to authorized users only, as the client files directly connect to the line-of-business applications.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="53abf-109">次の手順</span><span class="sxs-lookup"><span data-stu-id="53abf-109">Next steps</span></span> 
  
-   [<span data-ttu-id="53abf-110">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="53abf-110">Requirements for Single Sign-On</span></span>](../core/requirements-for-single-sign-on1.md)  
  
-   [<span data-ttu-id="53abf-111">シングル サインオンと BizTalk Adapter for JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="53abf-111">Single Sign-On and BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
  
-   [<span data-ttu-id="53abf-112">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="53abf-112">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications4.md)  
  
-   [<span data-ttu-id="53abf-113">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="53abf-113">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port1.md)