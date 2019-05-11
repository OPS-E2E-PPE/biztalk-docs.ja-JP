---
title: PeopleSoft Enterprise アダプター |Microsoft Docs
description: インストール、チュートリアルの手順、アーキテクチャについて説明します、SSO のセキュリティを使用して、アプリケーションを作成、バインド ファイルをインポートおよび BizTalk Adapter for PeopleSoft Enterprise では、BizTalk Server の使用時に、例外処理を追加
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c3dd7fd-3566-4063-a2fd-2acbe64d2885
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6963b6f5a291ee9086fdfb6f857dfcf93edf30fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291860"
---
# <a name="peoplesoft-enterprise-adapter"></a><span data-ttu-id="2e16d-103">PeopleSoft Enterprise Adapter</span><span class="sxs-lookup"><span data-stu-id="2e16d-103">PeopleSoft Enterprise Adapter</span></span>
<span data-ttu-id="2e16d-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、BizTalk Server アプリケーション内での PeopleSoft オブジェクトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2e16d-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise enables you to use PeopleSoft objects within your BizTalk Server application.</span></span> <span data-ttu-id="2e16d-105">次のセクションでは、PeopleSoft 固有の情報にアクセスするアダプターの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-105">The following sections discuss setting up the adapter to access PeopleSoft-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="2e16d-106">作業開始</span><span class="sxs-lookup"><span data-stu-id="2e16d-106">Get started</span></span>
<span data-ttu-id="2e16d-107">[開始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)アダプターをインストールし、ステップのチュートリアルを実行する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-107">[Get started](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) lists the steps to install the adapter, and step through some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="2e16d-108">Architecture</span><span class="sxs-lookup"><span data-stu-id="2e16d-108">Architecture</span></span>
<span data-ttu-id="2e16d-109">[アーキテクチャ](../core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise.md)インターフェイス メソッドをおよびこのアダプターを使用した検証について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-109">[Architecture](../core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise.md) describes the interface methods, and validation with this adapter.</span></span>

## <a name="security"></a><span data-ttu-id="2e16d-110">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2e16d-110">Security</span></span>
<span data-ttu-id="2e16d-111">[セキュリティ](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)BizTalk Serer このアダプターを使用するアプリケーションをセキュリティで保護するには、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-111">[Security](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="2e16d-112">アイテムを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-112">Create the artifacts</span></span>
<span data-ttu-id="2e16d-113">[アプリケーション アーティファクトを作成する](../core/developing-applications4.md)BizTalk 管理コンソールで、成果物を追加し、スキーマを Visual Studio に追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-113">[Create the application artifacts](../core/developing-applications4.md) shows you how to add the artifacts in BizTalk Administration, and add the schemas to Visual Studio.</span></span>

## <a name="import-apps"></a><span data-ttu-id="2e16d-114">アプリのインポート</span><span class="sxs-lookup"><span data-stu-id="2e16d-114">Import apps</span></span>
<span data-ttu-id="2e16d-115">[バインド ファイルをインポート](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)BizTalk 管理コンソールに、アプリケーションのバインド ファイルをインポートする方法について説明し、制限事項を経由します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-115">[Importing binding file](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="2e16d-116">例外処理</span><span class="sxs-lookup"><span data-stu-id="2e16d-116">Exception handling</span></span>
<span data-ttu-id="2e16d-117">[例外処理を使用して、](../core/using-biztalk-server-exception-handling2.md)例外を処理するオーケストレーションをさまざまな図形を追加する方法のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-117">[Use Exception Handling](../core/using-biztalk-server-exception-handling2.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2e16d-118">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2e16d-118">Troubleshooting</span></span>
<span data-ttu-id="2e16d-119">[トラブルシューティング](../core/troubleshooting-peoplesoft.md)一般的なエラーと状況、および Windows のイベント トレースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-119">[Troubleshooting](../core/troubleshooting-peoplesoft.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="component-interfaces"></a><span data-ttu-id="2e16d-120">コンポーネント インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e16d-120">Component interfaces</span></span>
<span data-ttu-id="2e16d-121">[参照](../core/technical-reference-for-peoplesoft-enterprise.md)メソッドの詳細を説明し、オーケストレーションをテストする XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-121">[Reference](../core/technical-reference-for-peoplesoft-enterprise.md) provides details on the methods, and generating XML to test your orchestrations.</span></span>

## <a name="ui-guidance"></a><span data-ttu-id="2e16d-122">UI ガイダンス</span><span class="sxs-lookup"><span data-stu-id="2e16d-122">UI guidance</span></span>
<span data-ttu-id="2e16d-123">[UI リファレンス](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)のダイアログ ボックスとこのアダプターによって使用されるウィザードの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-123">[UI Reference](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 