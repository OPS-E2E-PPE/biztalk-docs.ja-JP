---
title: TIBCO Enterprise Message Service アダプタ |Microsoft Docs
description: インストール、チュートリアルの手順、アーキテクチャについて説明します、SSO のセキュリティを使用して、アプリケーションを作成、バインド ファイルをインポートおよび BizTalk Server で TIBCO EMS 用 BizTalk アダプターを使用する場合は、例外処理を追加
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 362556d2-295c-4496-a429-ad7ecc44db76
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8f6b9612b16b02807d7f92a02d3c273ddb5f8fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395438"
---
# <a name="tibco-enterprise-message-service-adapter"></a><span data-ttu-id="8c06d-103">TIBCO Enterprise Message Service アダプター</span><span class="sxs-lookup"><span data-stu-id="8c06d-103">TIBCO Enterprise Message Service Adapter</span></span>
<span data-ttu-id="8c06d-104">Microsoft の BizTalk Adapter for TIBCO Enterprise Message Service を使用すると、キューおよび btsBizTalkServerNoVersion を使用して、TIBCO EMS によって管理されているトピックにパブリッシュおよびサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="8c06d-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service enables you to publish and subscribe to queues and topics managed by TIBCO EMS using btsBizTalkServerNoVersion.</span></span>  <span data-ttu-id="8c06d-105">次のセクションでは、概要、作成や、アプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8c06d-105">The following sections discuss getting started, creating applications, and more.</span></span>  
   
## <a name="get-started"></a><span data-ttu-id="8c06d-106">作業開始</span><span class="sxs-lookup"><span data-stu-id="8c06d-106">Get started</span></span>
<span data-ttu-id="8c06d-107">[開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)アダプターをインストールするアダプターの機能について説明し、一部のチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c06d-107">[Get started](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md) describes adapter features, installing the adapter, and includes some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="8c06d-108">Architecture</span><span class="sxs-lookup"><span data-stu-id="8c06d-108">Architecture</span></span>
<span data-ttu-id="8c06d-109">[アーキテクチャ](../core/planning-and-architecture16.md)方法アダプターはいくつか追加の要件を提供し、制限の一覧について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c06d-109">[Architecture](../core/planning-and-architecture16.md) describes how the adapter works, provides some additional requirements, and lists any limitations.</span></span>

## <a name="security"></a><span data-ttu-id="8c06d-110">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8c06d-110">Security</span></span>
<span data-ttu-id="8c06d-111">[セキュリティ](../core/security-in-biztalk-adapter-for-tibco-ems.md)BizTalk Serer このアダプターを使用するアプリケーションをセキュリティで保護するには、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c06d-111">[Security](../core/security-in-biztalk-adapter-for-tibco-ems.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="8c06d-112">アイテムを作成します。</span><span class="sxs-lookup"><span data-stu-id="8c06d-112">Create the artifacts</span></span>
<span data-ttu-id="8c06d-113">[アプリケーション アーティファクトを作成する](../core/developing-applications5.md)スキーマの生成を送信を作成し、オーケストレーション内でメッセージ コンテキスト プロパティを使用する方法と、このアダプターによって使用されるアイテムを受信する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c06d-113">[Create the application artifacts](../core/developing-applications5.md) lists the steps to generate schemas, create the send and receive artifacts used by this adapter, and how to use the message context properties within an orchestration.</span></span>

## <a name="import-apps"></a><span data-ttu-id="8c06d-114">アプリのインポート</span><span class="sxs-lookup"><span data-stu-id="8c06d-114">Import apps</span></span>
<span data-ttu-id="8c06d-115">[バインドをインポート](../core/deploying-biztalk-adapter-for-tibco-enterprise-message-service.md)BizTalk 管理コンソールに、アプリケーションのバインド ファイルをインポートする方法について説明し、制限事項を経由します。</span><span class="sxs-lookup"><span data-stu-id="8c06d-115">[Import bindings](../core/deploying-biztalk-adapter-for-tibco-enterprise-message-service.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="handle-exceptions"></a><span data-ttu-id="8c06d-116">例外を処理します。</span><span class="sxs-lookup"><span data-stu-id="8c06d-116">Handle exceptions</span></span>
<span data-ttu-id="8c06d-117">[BizTalk Server 例外処理を使用して、](../core/using-biztalk-server-exception-handling5.md)例外を処理するオーケストレーションをさまざまな図形を追加する方法のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8c06d-117">[Use BizTalk Server Exception Handling](../core/using-biztalk-server-exception-handling5.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8c06d-118">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8c06d-118">Troubleshooting</span></span>
 <span data-ttu-id="8c06d-119">[トラブルシューティング](../core/troubleshooting-tibco-enterprise-message-service.md)一般的なエラーと状況、および Windows のイベント トレースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8c06d-119">[Troubleshooting](../core/troubleshooting-tibco-enterprise-message-service.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>