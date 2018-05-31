---
title: JD Edwards EnterpriseOne アダプター |Microsoft ドキュメント
description: インストール、チュートリアルの手順、アーキテクチャの説明、SSO のセキュリティを使用して、アプリケーションの作成、バインド ファイルをインポートおよび BizTalk Adapter for j. d. の使用時に例外処理を追加 BizTalk Server で Edwards EnterpriseOne
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97f0f87a-59c3-4503-8da6-d6967dab820a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e1d82cafd20e8c86fbbf7daa42304ecb95c9aee
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015907"
---
# <a name="jd-edwards-enterpriseone-adapter"></a><span data-ttu-id="d1cbb-104">JD Edwards EnterpriseOne アダプタ</span><span class="sxs-lookup"><span data-stu-id="d1cbb-104">JD Edwards EnterpriseOne Adapter</span></span>
<span data-ttu-id="d1cbb-105">Microsoft BizTalk Adapter for j. d.</span><span class="sxs-lookup"><span data-stu-id="d1cbb-105">Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="d1cbb-106">Edwards EnterpriseOne では、BizTalk Server 内で JD Edwards EnterpriseOne のビジネス関数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-106">Edwards EnterpriseOne enables you to use JD Edwards EnterpriseOne business functions within BizTalk Server.</span></span> <span data-ttu-id="d1cbb-107">次のセクションでは、アダプターをセットアップして JD Edwards EnterpriseOne 固有の情報にアクセスする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-107">The following sections discuss setting up the adapter to access JD Edwards EnterpriseOne-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="d1cbb-108">作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-108">Get started</span></span>
<span data-ttu-id="d1cbb-109">[開始](../core/getting-started-with-biztalk-adapter-for-jd-edwards-enterpriseone.md)アダプターをインストールし、ステップのチュートリアルを実行する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-109">[Get started](../core/getting-started-with-biztalk-adapter-for-jd-edwards-enterpriseone.md) lists the steps to install the adapter, and step through some tutorials.</span></span>

## <a name="architecture"></a><span data-ttu-id="d1cbb-110">Architecture</span><span class="sxs-lookup"><span data-stu-id="d1cbb-110">Architecture</span></span>
<span data-ttu-id="d1cbb-111">[アーキテクチャ](../core/architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone.md)デザイン時をについて説明し、アダプターの時間要素を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-111">[Architecture](../core/architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone.md) describes the design time and run time elements of the adapter.</span></span>

## <a name="security"></a><span data-ttu-id="d1cbb-112">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d1cbb-112">Security</span></span>
<span data-ttu-id="d1cbb-113">[セキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)BizTalk Serer このアダプターを使用するアプリケーションをセキュリティで保護するには、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-113">[Security](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="d1cbb-114">成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-114">Create the artifacts</span></span>
<span data-ttu-id="d1cbb-115">[アプリケーションのアイテムを作成する](../core/developing-applications2.md)Visual Studio および BizTalk 管理コンソールで、アイテムを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-115">[Create the application artifacts](../core/developing-applications2.md) shows you how to add the artifacts in BizTalk Administration, and in Visual Studio.</span></span> <span data-ttu-id="d1cbb-116">また、オーケストレーションでメッセージ コンテキスト プロパティを使用する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-116">It also shows how to use message context properties in an orchestration.</span></span>

## <a name="import-your-app"></a><span data-ttu-id="d1cbb-117">アプリをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-117">Import your app</span></span>
<span data-ttu-id="d1cbb-118">[アプリケーションを配置する](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)BizTalk 管理コンソールにアプリケーションのバインド ファイルをインポートする方法について説明し、制限を超えた。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-118">[Deploying your application](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md) discusses how to import your application binding file into BizTalk Administration, and goes over any limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="d1cbb-119">例外処理</span><span class="sxs-lookup"><span data-stu-id="d1cbb-119">Exception handling</span></span>
<span data-ttu-id="d1cbb-120">[BizTalk Server 例外処理](../core/using-biztalk-server-exception-handling3.md)例外を処理するオーケストレーションを別の図形の追加に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-120">[BizTalk Server Exception Handling](../core/using-biztalk-server-exception-handling3.md) provides guidance on adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d1cbb-121">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d1cbb-121">Troubleshooting</span></span>
<span data-ttu-id="d1cbb-122">[アダプターのトラブルシューティングを行う](../core/troubleshooting-jd-edwards-enterpriseone.md)一般的なエラーと状況、および Event Tracing for Windows をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-122">[Troubleshoot the adapter](../core/troubleshooting-jd-edwards-enterpriseone.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="reference"></a><span data-ttu-id="d1cbb-123">リファレンス</span><span class="sxs-lookup"><span data-stu-id="d1cbb-123">Reference</span></span>
<span data-ttu-id="d1cbb-124">[テクニカル リファレンス](../core/technical-reference6.md)サンプル ファイルと、このアダプターによって使用されるサンプル データ型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-124">[Technical reference](../core/technical-reference6.md) includes sample files and sample data types used by this adapter.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d1cbb-125">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="d1cbb-125">UI reference</span></span>
<span data-ttu-id="d1cbb-126">[UI リファレンス](../core/ui-reference-for-biztalk-adapter-for-jd-edwards-enterpriseone.md)の詳細 ダイアログ ボックスおよびこのアダプターによって使用されるウィザードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d1cbb-126">[UI reference](../core/ui-reference-for-biztalk-adapter-for-jd-edwards-enterpriseone.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 