---
title: エンタープライズ アプリケーション アダプター |Microsoft Docs
description: Microsoft BizTalk Adapters for Enterprise Applications には、BizTalk Server で使用するには、JD Edwards EnterpriseOne、JD Edwards OneWorld では、PeopleSoft Enterprise、TIBCO Enterprise Message Service と TIBCO Rendezvous が含まれています。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1960a5a-d627-42ce-8898-5df444846fea
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6f5f80161297281aeb00ab6d04dd5aa4e890cdd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367265"
---
# <a name="enterprise-applications-adapters-in-biztalk-server"></a><span data-ttu-id="abef7-103">BizTalk Server のエンタープライズ アプリケーション アダプター</span><span class="sxs-lookup"><span data-stu-id="abef7-103">Enterprise Applications adapters in BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="abef7-104">概要</span><span class="sxs-lookup"><span data-stu-id="abef7-104">Overview</span></span>

<span data-ttu-id="abef7-105">Microsoft BizTalk Server には、相互のやり取りにエンタープライズ アプリケーションを有効にするアダプターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="abef7-105">Microsoft BizTalk Server includes adapters that enable enterprise applications to interface with each other.</span></span> <span data-ttu-id="abef7-106">エンタープライズ アプリケーションには、次のアダプターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="abef7-106">The Enterprise Applications includes the following adapters:</span></span>  

* <span data-ttu-id="abef7-107">JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="abef7-107">JD Edwards EnterpriseOne</span></span>
* <span data-ttu-id="abef7-108">JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="abef7-108">JD Edwards OneWorld</span></span>
* <span data-ttu-id="abef7-109">PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="abef7-109">PeopleSoft Enterprise</span></span>
* <span data-ttu-id="abef7-110">TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="abef7-110">TIBCO Enterprise Message Service</span></span>
* <span data-ttu-id="abef7-111">TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="abef7-111">TIBCO Rendezvous</span></span> 

<span data-ttu-id="abef7-112">これらのアダプターを使用して、これらのデータを取得する、オンプレミスの基幹業務 (LOB) システムに接続し、データを配置できます。</span><span class="sxs-lookup"><span data-stu-id="abef7-112">Using these adapters, you can connect to these on-premises line-of-business (LOB) systems to get data, and put data.</span></span> 

## <a name="install"></a><span data-ttu-id="abef7-113">インストール</span><span class="sxs-lookup"><span data-stu-id="abef7-113">Install</span></span>
<span data-ttu-id="abef7-114">エンタープライズ アプリケーション アダプターは BizTalk Server に含まれています。</span><span class="sxs-lookup"><span data-stu-id="abef7-114">The Enterprise Applications adapters are included with BizTalk Server.</span></span> <span data-ttu-id="abef7-115">特定のインストールの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abef7-115">For the specific installation steps, see:</span></span>

[<span data-ttu-id="abef7-116">インストールし、Microsoft BizTalk Adapters for Enterprise Applications に構成します。</span><span class="sxs-lookup"><span data-stu-id="abef7-116">Install and configure the Microsoft BizTalk Adapters for Enterprise Applications</span></span>](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)

## <a name="jd-edwards-enterpriseone-adapter"></a><span data-ttu-id="abef7-117">JD Edwards EnterpriseOne アダプター</span><span class="sxs-lookup"><span data-stu-id="abef7-117">JD Edwards EnterpriseOne adapter</span></span>

<span data-ttu-id="abef7-118">[Microsoft の BizTalk Adapter for JD Edwards EnterpriseOne](../core/jd-edwards-enterpriseone-adapter.md)を開始する方法についてのチュートリアルが含まれています、デザイン時に、SSO を使用して、アプリケーションのセキュリティ保護して、オーケストレーション内でのメッセージ コンテキスト プロパティを使用して、実行時に、アーキテクチャについて説明します.</span><span class="sxs-lookup"><span data-stu-id="abef7-118">[Microsoft BizTalk Adapter for JD Edwards EnterpriseOne](../core/jd-edwards-enterpriseone-adapter.md) includes a tutorial to get started, describes the architecture at run time and design time, using SSO to secure your applications, and using message context properties within an orchestration.</span></span> <span data-ttu-id="abef7-119">バインド ファイルを使用して、例外処理とアダプターのトラブルシューティングについては、します。</span><span class="sxs-lookup"><span data-stu-id="abef7-119">Using binding files, exception handling, and troubleshooting the adapter are also covered.</span></span> 

## <a name="jd-edwards-oneworld-adapter"></a><span data-ttu-id="abef7-120">JD Edwards OneWorld アダプター</span><span class="sxs-lookup"><span data-stu-id="abef7-120">JD Edwards OneWorld adapter</span></span>

<span data-ttu-id="abef7-121">[Microsoft の BizTalk Adapter for JD Edwards OneWorld](../core/jd-edwards-oneworld-adapter.md)を開始する方法についてのチュートリアルが含まれています、アーキテクチャと制限事項、SSO を使用して、アプリケーションのセキュリティ保護して、オーケストレーション内でのメッセージ コンテキスト プロパティの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="abef7-121">[Microsoft BizTalk Adapter for JD Edwards OneWorld](../core/jd-edwards-oneworld-adapter.md) includes a tutorial to get started, describes the architecture and limitations, using SSO to secure your applications, and using message context properties within an orchestration.</span></span> <span data-ttu-id="abef7-122">バインド ファイルを使用して、例外処理とアダプターのトラブルシューティングについては、します。</span><span class="sxs-lookup"><span data-stu-id="abef7-122">Using binding files, exception handling, and troubleshooting the adapter are also covered.</span></span> 

## <a name="peoplesoft-enterprise-adapter"></a><span data-ttu-id="abef7-123">PeopleSoft Enterprise アダプター</span><span class="sxs-lookup"><span data-stu-id="abef7-123">PeopleSoft Enterprise adapter</span></span>

<span data-ttu-id="abef7-124">[Microsoft BizTalk Adapter for PeopleSoft Enterprise](../core/peoplesoft-enterprise-adapter.md)を開始するいくつかのチュートリアルが含まれています、アーキテクチャと SSO を使用して、アプリケーションのセキュリティ保護して、送信の制限について説明、および PeopleSoft を受信します。</span><span class="sxs-lookup"><span data-stu-id="abef7-124">[Microsoft BizTalk Adapter for PeopleSoft Enterprise](../core/peoplesoft-enterprise-adapter.md) includes several tutorials to get started, describes the architecture and limitations, using SSO to secure your applications, and sending and receive with PeopleSoft.</span></span> <span data-ttu-id="abef7-125">バインド ファイルを使用して、例外処理とアダプターのトラブルシューティングについては、します。</span><span class="sxs-lookup"><span data-stu-id="abef7-125">Using binding files, exception handling, and troubleshooting the adapter are also covered.</span></span> 

## <a name="tibco-enterprise-message-service-adapter"></a><span data-ttu-id="abef7-126">TIBCO Enterprise Message Service アダプター</span><span class="sxs-lookup"><span data-stu-id="abef7-126">TIBCO Enterprise Message Service adapter</span></span>

<span data-ttu-id="abef7-127">[Microsoft の BizTalk Adapter for TIBCO Enterprise Message Service](../core/tibco-enterprise-message-service-adapter.md)を開始するいくつかのチュートリアルが含まれています、アーキテクチャと、制限事項について説明し、SSO を使用して、アプリケーションをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="abef7-127">[Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tibco-enterprise-message-service-adapter.md) includes several tutorials to get started, describes the architecture and limitations, and using SSO to secure your applications.</span></span> <span data-ttu-id="abef7-128">例外処理、およびアダプターのトラブルシューティングも説明します。</span><span class="sxs-lookup"><span data-stu-id="abef7-128">Exception handling, and troubleshooting the adapter are also covered.</span></span> 

## <a name="tibco-rendezvous-adapter"></a><span data-ttu-id="abef7-129">TIBCO Rendezvous アダプター</span><span class="sxs-lookup"><span data-stu-id="abef7-129">TIBCO Rendezvous adapter</span></span>
<span data-ttu-id="abef7-130">[Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tibco-rendezvous-adapter.md)アーキテクチャと SSO を使用して、アプリケーションのセキュリティ保護して、送信の制限について説明します、TIBCO で受信を開始するいくつかのチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="abef7-130">[Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tibco-rendezvous-adapter.md) includes several tutorials to get started, describes the architecture and limitations, using SSO to secure your applications, and sending and receive with TIBCO.</span></span> <span data-ttu-id="abef7-131">例外処理、およびアダプターのトラブルシューティングも説明します。</span><span class="sxs-lookup"><span data-stu-id="abef7-131">Exception handling, and troubleshooting the adapter are also covered.</span></span> 

