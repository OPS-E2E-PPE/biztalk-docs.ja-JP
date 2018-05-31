---
title: TIBCO Enterprise Message Service アダプタ |Microsoft ドキュメント
description: インストール、チュートリアルの手順、アーキテクチャについて説明、SSO のセキュリティを使用して、アプリケーションの作成、バインド ファイルをインポートおよび BizTalk Server で TIBCO EMS の BizTalk アダプターを使用する場合は、例外処理を追加
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
ms.openlocfilehash: 988c7993dd407cb90e267e713a3195f897de9ceb
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013721"
---
# <a name="tibco-enterprise-message-service-adapter"></a><span data-ttu-id="e4342-103">TIBCO Enterprise Message Service アダプタ</span><span class="sxs-lookup"><span data-stu-id="e4342-103">TIBCO Enterprise Message Service Adapter</span></span>
<span data-ttu-id="e4342-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service を使用すると、キューおよびトピック btsBizTalkServerNoVersion を使用して TIBCO EMS によって管理されるを公開およびサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="e4342-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service enables you to publish and subscribe to queues and topics managed by TIBCO EMS using btsBizTalkServerNoVersion.</span></span>  <span data-ttu-id="e4342-105">次のセクションでは、作業の開始、作成するアプリケーション、および詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4342-105">The following sections discuss getting started, creating applications, and more.</span></span>  
   
## <a name="get-started"></a><span data-ttu-id="e4342-106">作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="e4342-106">Get started</span></span>
<span data-ttu-id="e4342-107">[開始](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)アダプターをインストールするアダプターの機能を説明し、いくつかのチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4342-107">[Get started](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md) describes adapter features, installing the adapter, and includes some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="e4342-108">Architecture</span><span class="sxs-lookup"><span data-stu-id="e4342-108">Architecture</span></span>
<span data-ttu-id="e4342-109">[アーキテクチャ](../core/planning-and-architecture16.md)および方法について説明アダプターの動作、いくつか追加の要件は、制限事項を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e4342-109">[Architecture](../core/planning-and-architecture16.md) describes how the adapter works, provides some additional requirements, and lists any limitations.</span></span>

## <a name="security"></a><span data-ttu-id="e4342-110">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e4342-110">Security</span></span>
<span data-ttu-id="e4342-111">[セキュリティ](../core/security-in-biztalk-adapter-for-tibco-ems.md)BizTalk Serer このアダプターを使用するアプリケーションをセキュリティで保護するには、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4342-111">[Security](../core/security-in-biztalk-adapter-for-tibco-ems.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="e4342-112">成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="e4342-112">Create the artifacts</span></span>
<span data-ttu-id="e4342-113">[アプリケーションのアイテムを作成する](../core/developing-applications5.md)スキーマを生成する、送信を作成し、オーケストレーション内でメッセージ コンテキスト プロパティを使用する方法と、このアダプターによって使用されるアイテムを受信する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4342-113">[Create the application artifacts](../core/developing-applications5.md) lists the steps to generate schemas, create the send and receive artifacts used by this adapter, and how to use the message context properties within an orchestration.</span></span>

## <a name="import-apps"></a><span data-ttu-id="e4342-114">アプリをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e4342-114">Import apps</span></span>
<span data-ttu-id="e4342-115">[バインドをインポート](../core/deploying-biztalk-adapter-for-tibco-enterprise-message-service.md)BizTalk 管理コンソールにアプリケーションのバインド ファイルをインポートする方法について説明し、制限を超えた。</span><span class="sxs-lookup"><span data-stu-id="e4342-115">[Import bindings](../core/deploying-biztalk-adapter-for-tibco-enterprise-message-service.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="handle-exceptions"></a><span data-ttu-id="e4342-116">例外処理</span><span class="sxs-lookup"><span data-stu-id="e4342-116">Handle exceptions</span></span>
<span data-ttu-id="e4342-117">[BizTalk Server 例外処理を使用して](../core/using-biztalk-server-exception-handling5.md)例外を処理するオーケストレーションを別の図形の追加に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="e4342-117">[Use BizTalk Server Exception Handling](../core/using-biztalk-server-exception-handling5.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e4342-118">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e4342-118">Troubleshooting</span></span>
 <span data-ttu-id="e4342-119">[トラブルシューティング](../core/troubleshooting-tibco-enterprise-message-service.md)一般的なエラーと状況、および Event Tracing for Windows をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e4342-119">[Troubleshooting](../core/troubleshooting-tibco-enterprise-message-service.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>