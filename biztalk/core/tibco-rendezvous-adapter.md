---
title: TIBCO Rendezvous アダプター |Microsoft Docs
description: インストール、チュートリアルの手順、アーキテクチャについて説明します、SSO のセキュリティを使用して、アプリケーションを作成、バインド ファイルをインポートおよび BizTalk Server で TIBCO Rendezvous を BizTalk アダプターを使用する場合は、例外処理を追加
ms.custom: ''
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0528954d-11b4-449b-8057-30d463104fef
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 437d0ba281a724b47b8ccfb7c15846d4cfaa8bb8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379813"
---
# <a name="tibco-rendezvous-adapter"></a><span data-ttu-id="e3379-103">TIBCO Rendezvous アダプター</span><span class="sxs-lookup"><span data-stu-id="e3379-103">TIBCO Rendezvous Adapter</span></span>
<span data-ttu-id="e3379-104">Microsoft BizTalk Adapter for TIBCO Rendezvous では、BizTalk Server 内で TIBCO Rendezvous ビジネス関数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e3379-104">Microsoft BizTalk Adapter for TIBCO Rendezvous enables you to use TIBCO Rendezvous business functions within BizTalk Server.</span></span> <span data-ttu-id="e3379-105">次のセクションでは、TIBCO Rendezvous 固有情報にアクセスするアダプターの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3379-105">The following sections discuss setting up the adapter to access TIBCO Rendezvous-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="e3379-106">作業開始</span><span class="sxs-lookup"><span data-stu-id="e3379-106">Get started</span></span>
<span data-ttu-id="e3379-107">[開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)さまざまなメッセージと概念について説明し、インストール、スキーマ、および制限事項の詳細も提供します。</span><span class="sxs-lookup"><span data-stu-id="e3379-107">[Get started](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) describes the different messages and concepts, and also provides details on installation, schemas, and limitations.</span></span> <span data-ttu-id="e3379-108">このアダプターを使用してデータを送受信するためのいくつかのチュートリアルの手順もします。</span><span class="sxs-lookup"><span data-stu-id="e3379-108">ALso step through some tutorials to receive and send data using this adapter.</span></span>

## <a name="architecture"></a><span data-ttu-id="e3379-109">Architecture</span><span class="sxs-lookup"><span data-stu-id="e3379-109">Architecture</span></span>
<span data-ttu-id="e3379-110">[アーキテクチャ](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md)接続、およびメッセージを渡す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3379-110">[Architecture](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md) describes the connectivity, and how messages are passed.</span></span>

## <a name="security"></a><span data-ttu-id="e3379-111">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e3379-111">Security</span></span>
<span data-ttu-id="e3379-112">[セキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)BizTalk Serer このアダプターを使用するアプリケーションをセキュリティで保護するには、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3379-112">[Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-applications"></a><span data-ttu-id="e3379-113">アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3379-113">Create applications</span></span>
<span data-ttu-id="e3379-114">[アプリケーション アーティファクトを作成する](../core/developing-applications1.md)受信を追加し、BizTalk 管理コンソールでの成果物を送信する方法を示します、コンテキスト プロパティをメッセージとデータ型のマッピング、およびメッセージで詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="e3379-114">[Create application artifacts](../core/developing-applications1.md) shows you how to add the receive and send artifacts in BizTalk Administration, provides details on message and data type mapping, and message context properties.</span></span>

## <a name="importing-assemblies"></a><span data-ttu-id="e3379-115">アセンブリをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e3379-115">Importing assemblies</span></span>
<span data-ttu-id="e3379-116">[ポートとアセンブリをインポート](../core/deploying-biztalk-adapter-for-tibco-rendezvous.md)BizTalk 管理コンソールに、アプリケーションのバインド ファイルをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3379-116">[Import ports and assemblies](../core/deploying-biztalk-adapter-for-tibco-rendezvous.md) discusses how to import your application binding file into BizTalk Administration.</span></span>

## <a name="handle-exceptions"></a><span data-ttu-id="e3379-117">例外を処理します。</span><span class="sxs-lookup"><span data-stu-id="e3379-117">Handle exceptions</span></span>
<span data-ttu-id="e3379-118">[例外処理](../core/using-biztalk-server-exception-handling4.md)例外を処理するオーケストレーションをさまざまな図形を追加する方法のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e3379-118">[Exception handling](../core/using-biztalk-server-exception-handling4.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="e3379-119">[トラブルシューティング]</span><span class="sxs-lookup"><span data-stu-id="e3379-119">Troubleshoot</span></span>
<span data-ttu-id="e3379-120">[TIBCO Rendezvous のトラブルシューティング](../core/troubleshooting-tibco-rendezvous.md)Windows のイベント トレーシングの使用の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3379-120">[Troubleshooting TIBCO Rendezvous](../core/troubleshooting-tibco-rendezvous.md) includes details on using Event Tracing for Windows.</span></span>