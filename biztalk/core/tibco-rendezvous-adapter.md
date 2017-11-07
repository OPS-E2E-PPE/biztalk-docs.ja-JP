---
title: "TIBCO Rendezvous アダプター |Microsoft ドキュメント"
description: "インストール、チュートリアルの手順、アーキテクチャについて説明、SSO のセキュリティを使用して、アプリケーションの作成、バインド ファイルをインポートおよび BizTalk Server で TIBCO Rendezvous を BizTalk アダプターを使用する場合は、例外処理を追加"
ms.custom: 
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0528954d-11b4-449b-8057-30d463104fef
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b12b4c8382019372efca91b11eda4efa8e3f4b4a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-rendezvous-adapter"></a><span data-ttu-id="19bc2-103">TIBCO Rendezvous アダプタ</span><span class="sxs-lookup"><span data-stu-id="19bc2-103">TIBCO Rendezvous Adapter</span></span>
<span data-ttu-id="19bc2-104">Microsoft BizTalk Adapter for TIBCO Rendezvous を使用すると、BizTalk Server 内で TIBCO Rendezvous ビジネス関数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="19bc2-104">Microsoft BizTalk Adapter for TIBCO Rendezvous enables you to use TIBCO Rendezvous business functions within BizTalk Server.</span></span> <span data-ttu-id="19bc2-105">次のセクションでは、アダプターをセットアップして TIBCO Rendezvous 固有の情報にアクセスする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="19bc2-105">The following sections discuss setting up the adapter to access TIBCO Rendezvous-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="19bc2-106">作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="19bc2-106">Get started</span></span>
<span data-ttu-id="19bc2-107">[開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)さまざまなメッセージと概念について説明し、詳細をインストール、スキーマ、および制限事項についても説明します。</span><span class="sxs-lookup"><span data-stu-id="19bc2-107">[Get started](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) describes the different messages and concepts, and also provides details on installation, schemas, and limitations.</span></span> <span data-ttu-id="19bc2-108">このアダプターを使用してデータを送受信するためのチュートリアルの手順もします。</span><span class="sxs-lookup"><span data-stu-id="19bc2-108">ALso step through some tutorials to receive and send data using this adapter.</span></span>

## <a name="architecture"></a><span data-ttu-id="19bc2-109">Architecture</span><span class="sxs-lookup"><span data-stu-id="19bc2-109">Architecture</span></span>
<span data-ttu-id="19bc2-110">[アーキテクチャ](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md)接続、およびメッセージを渡す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19bc2-110">[Architecture](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md) describes the connectivity, and how messages are passed.</span></span>

## <a name="security"></a><span data-ttu-id="19bc2-111">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="19bc2-111">Security</span></span>
<span data-ttu-id="19bc2-112">[セキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)BizTalk Serer このアダプターを使用するアプリケーションをセキュリティで保護するには、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="19bc2-112">[Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-applications"></a><span data-ttu-id="19bc2-113">アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="19bc2-113">Create applications</span></span>
<span data-ttu-id="19bc2-114">[アプリケーションのアイテムを作成する](../core/developing-applications1.md)受信を追加し、BizTalk 管理コンソールでアイテムを送信する方法を示します、メッセージとデータ型のマッピング、およびメッセージのコンテキスト プロパティの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="19bc2-114">[Create application artifacts](../core/developing-applications1.md) shows you how to add the receive and send artifacts in BizTalk Administration, provides details on message and data type mapping, and message context properties.</span></span>

## <a name="importing-assemblies"></a><span data-ttu-id="19bc2-115">アセンブリをインポートします。</span><span class="sxs-lookup"><span data-stu-id="19bc2-115">Importing assemblies</span></span>
<span data-ttu-id="19bc2-116">[ポートとアセンブリをインポート](../core/deploying-biztalk-adapter-for-tibco-rendezvous.md)BizTalk 管理コンソールにアプリケーションのバインド ファイルをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19bc2-116">[Import ports and assemblies](../core/deploying-biztalk-adapter-for-tibco-rendezvous.md) discusses how to import your application binding file into BizTalk Administration.</span></span>

## <a name="handle-exceptions"></a><span data-ttu-id="19bc2-117">例外処理</span><span class="sxs-lookup"><span data-stu-id="19bc2-117">Handle exceptions</span></span>
<span data-ttu-id="19bc2-118">[例外処理](../core/using-biztalk-server-exception-handling4.md)例外を処理するオーケストレーションを別の図形の追加に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="19bc2-118">[Exception handling](../core/using-biztalk-server-exception-handling4.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="19bc2-119">[トラブルシューティング]</span><span class="sxs-lookup"><span data-stu-id="19bc2-119">Troubleshoot</span></span>
<span data-ttu-id="19bc2-120">[TIBCO Rendezvous のトラブルシューティング](../core/troubleshooting-tibco-rendezvous.md)Event Tracing for Windows の使用の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19bc2-120">[Troubleshooting TIBCO Rendezvous](../core/troubleshooting-tibco-rendezvous.md) includes details on using Event Tracing for Windows.</span></span>