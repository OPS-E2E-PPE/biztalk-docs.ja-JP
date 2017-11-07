---
title: "JD Edwards OneWorld アダプター |Microsoft ドキュメント"
description: "インストール、チュートリアルの手順、アーキテクチャの説明、SSO のセキュリティを使用して、アプリケーションの作成、バインド ファイルをインポートおよび BizTalk Adapter for j. d. の使用時に例外処理を追加 BizTalk Server で Edwards OneWorld"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5df8cd89-d9df-41ca-9a2c-b9d7fbcd06f2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bde93503bff679faf2717edefb386aa2f43fc3e
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="jd-edwards-oneworld-adapter"></a><span data-ttu-id="101bb-104">JD Edwards OneWorld アダプタ</span><span class="sxs-lookup"><span data-stu-id="101bb-104">JD Edwards OneWorld Adapter</span></span>
<span data-ttu-id="101bb-105">Microsoft BizTalk Adapter for JD Edwards OneWorld により、JD Edwards OneWorld のビジネス関数を BizTalk Server で利用することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="101bb-105">Microsoft BizTalk Adapter for JD Edwards OneWorld enables you to use JD Edwards OneWorld business functions within BizTalk Server.</span></span> <span data-ttu-id="101bb-106">ここでは、JD Edwards OneWorld 固有の情報にアクセスするように BizTalk Adapter for JD Edwards OneWorld を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="101bb-106">The following sections discuss setting up BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld-specific information.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="101bb-107">作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="101bb-107">Get started</span></span> 
<span data-ttu-id="101bb-108">[開始](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md)アダプターをインストールし、ステップ チュートリアルを実行する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="101bb-108">[Get started](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md) lists the steps to install the adapter, and step through a tutorial.</span></span>

## <a name="architecture"></a><span data-ttu-id="101bb-109">Architecture</span><span class="sxs-lookup"><span data-stu-id="101bb-109">Architecture</span></span>
<span data-ttu-id="101bb-110">[アーキテクチャ](../core/planning-and-architecture17.md)アダプターのしくみ、どのインスタンスと関数がプールされており、デザイン時および実行時の制限事項にクエリと取得を一覧表示する場合、について詳しく説明し、このアダプターで複数の注文のアイテムを使用します。</span><span class="sxs-lookup"><span data-stu-id="101bb-110">[Architecture](../core/planning-and-architecture17.md) details how the adapter works, how instances and functions are pooled at design time and run time, limitations when  querying and retrieving lists, and using multi-order items with this adapter.</span></span>

## <a name="security"></a><span data-ttu-id="101bb-111">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="101bb-111">Security</span></span>
<span data-ttu-id="101bb-112">[BizTalk Adapter for JD Edwards OneWorld セキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)BizTalk Serer このアダプターを使用するアプリケーションをセキュリティで保護するには、エンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="101bb-112">[Security in BizTalk Adapter for JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) involves using Enterprise Single Sign-on (SSO) within BizTalk Serer to secure your applications that use this adapter.</span></span>

## <a name="create-the-artifacts"></a><span data-ttu-id="101bb-113">成果物を作成します。</span><span class="sxs-lookup"><span data-stu-id="101bb-113">Create the artifacts</span></span>
<span data-ttu-id="101bb-114">[アプリケーションのアイテムを作成する](../core/developing-applications3.md)Visual Studio および BizTalk 管理コンソールで、アイテムを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="101bb-114">[Create the application artifacts](../core/developing-applications3.md) shows you how to add the artifacts in BizTalk Administration, and in Visual Studio.</span></span> <span data-ttu-id="101bb-115">また、オーケストレーションでメッセージ コンテキスト プロパティを使用する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="101bb-115">It also shows how to use message context properties in an orchestration.</span></span>

## <a name="import-your-app"></a><span data-ttu-id="101bb-116">アプリをインポートします。</span><span class="sxs-lookup"><span data-stu-id="101bb-116">Import your app</span></span>
<span data-ttu-id="101bb-117">[BizTalk Adapter for JD Edwards OneWorld の展開](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md)BizTalk 管理コンソールにアプリケーションのバインド ファイルをインポートする方法について説明し、制限事項経由で送信します。</span><span class="sxs-lookup"><span data-stu-id="101bb-117">[Deploying BizTalk Adapter for JD Edwards OneWorld](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md) discusses how to import your application binding file into BizTalk Administration, and goes over the limitations.</span></span> 

## <a name="exception-handling"></a><span data-ttu-id="101bb-118">例外処理</span><span class="sxs-lookup"><span data-stu-id="101bb-118">Exception handling</span></span> 
<span data-ttu-id="101bb-119">[BizTalk Server 例外処理](../core/using-biztalk-server-exception-handling1.md)jdearglist.txt ファイルを更新し、例外を処理するオーケストレーションを別の図形の追加に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="101bb-119">[BizTalk Server exception handling](../core/using-biztalk-server-exception-handling1.md) provides guidance on updating the jdearglist.txt file, and adding different shapes to your orchestration to handle exceptions.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="101bb-120">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="101bb-120">Troubleshooting</span></span>
<span data-ttu-id="101bb-121">[トラブルシューティング](../core/troubleshooting-jd-edwards-oneworld.md)一般的なエラーと状況、および Event Tracing for Windows をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="101bb-121">[Troubleshooting](../core/troubleshooting-jd-edwards-oneworld.md) describes some common errors and situations, and discusses Event Tracing for Windows.</span></span>

## <a name="data-types"></a><span data-ttu-id="101bb-122">データ型</span><span class="sxs-lookup"><span data-stu-id="101bb-122">Data Types</span></span>
<span data-ttu-id="101bb-123">[付録: データ型](../core/appendix-a-data-types.md)このアダプターによって使用されるサンプルのデータ型を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="101bb-123">[Appendix: Data Types](../core/appendix-a-data-types.md) lists the sample data types used by this adapter.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="101bb-124">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="101bb-124">UI reference</span></span>
<span data-ttu-id="101bb-125">[BizTalk Adapter for JDE OneWorld の UI リファレンス](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)の詳細 ダイアログ ボックスおよびこのアダプターによって使用されるウィザードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="101bb-125">[UI Reference for BizTalk Adapter for JDE OneWorld](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md) provides details on the dialog boxes and wizards used by this adapter.</span></span> 