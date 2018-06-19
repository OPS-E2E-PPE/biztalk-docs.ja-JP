---
title: Microsoft BizTalk Adapter 用 Siebel eBusiness アプリケーションのドキュメント |Microsoft ドキュメント
description: 取得開始されると、アーキテクチャ、セキュリティ、アプリを開発、メッセージ スキーマ、および BizTalk Adapter Pack の Siebel アダプターのトラブルシューティング
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39cc8e02-d37f-4f8a-91f9-d87d312434a1
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73c63b6a6a4115251ef1959090efc5bdd74b489
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222162"
---
# <a name="microsoft-biztalk-adapter-for-siebel-ebusiness-applications-documentation"></a><span data-ttu-id="c75b9-103">Microsoft BizTalk Adapter 用 Siebel eBusiness アプリケーションのドキュメント</span><span class="sxs-lookup"><span data-stu-id="c75b9-103">Microsoft BizTalk Adapter for Siebel eBusiness Applications documentation</span></span>
<span data-ttu-id="c75b9-104">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]さまざまなアダプターの動作、アダプターを使用するアプリケーションを作成する方法について理解するのに役立つリソースが含まれています、別の接続オプションなどについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c75b9-104">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] includes a variety of resources to help you understand how the adapter works, how to create applications that use the adapter, describes the different connection options, and more.</span></span>
  
## <a name="get-started"></a><span data-ttu-id="c75b9-105">作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="c75b9-105">Get started</span></span> 
<span data-ttu-id="c75b9-106">![はじめにアイコン](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [開始](../../adapters-and-accelerators/adapter-siebel/get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications.md)カスタム Rfc をインストールする手順を一覧表示、アダプターのような機能の概要を説明し、制限事項、し、いくつかのアダプターを実際に体験するためのチュートリアルがあります。</span><span class="sxs-lookup"><span data-stu-id="c75b9-106">![Getting started icon](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [Get started](../../adapters-and-accelerators/adapter-siebel/get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications.md) lists the steps to install custom RFCs, provides an overview of the adapter including features and limitations, and also has some tutorials to get you some hands-on experience with the adapter.</span></span>

## <a name="architecture"></a><span data-ttu-id="c75b9-107">Architecture</span><span class="sxs-lookup"><span data-stu-id="c75b9-107">Architecture</span></span> 
<span data-ttu-id="c75b9-108">![アダプター アーキテクチャ アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/4af6a1c5-948f-4bf7-bb56-4d63a47f4825.gif "4af6a1c5-948f-4bf7-bb56-4d63a47f4825") [アーキテクチャの概要](../../adapters-and-accelerators/adapter-siebel/architecture-overview-of-the-biztalk-adapter-for-siebel-ebusiness-applications.md)アダプターの使用に関する情報が含まれています、WCF などのしくみです。</span><span class="sxs-lookup"><span data-stu-id="c75b9-108">![Adapter Architecture icon](../../adapters-and-accelerators/adapter-oracle-database/media/4af6a1c5-948f-4bf7-bb56-4d63a47f4825.gif "4af6a1c5-948f-4bf7-bb56-4d63a47f4825") [Architecture overview](../../adapters-and-accelerators/adapter-siebel/architecture-overview-of-the-biztalk-adapter-for-siebel-ebusiness-applications.md) includes info on consuming the adapter, how it works with WCF, and more.</span></span>

## <a name="security"></a><span data-ttu-id="c75b9-109">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c75b9-109">Security</span></span>
<span data-ttu-id="c75b9-110">![コミュニティ リソース アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/community.gif "コミュニティ")[セキュリティ](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)のベスト プラクティスと、アダプターを使用して、メッセージをセキュリティ保護の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="c75b9-110">![Community resources icon](../../adapters-and-accelerators/adapter-oracle-database/media/community.gif "Community") [Security](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md) provides best practices and more to secure your messages using the adapter.</span></span>

## <a name="developing-apps"></a><span data-ttu-id="c75b9-111">アプリの開発</span><span class="sxs-lookup"><span data-stu-id="c75b9-111">Developing apps</span></span>
<span data-ttu-id="c75b9-112">![アダプター開発アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/44af70c9-cab1-4201-9912-d115cbc7e16f.gif "44af70c9-cab1-4201-9912-d115cbc7e16f") [Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)BizTalk Server、Windows で、アダプターを使用する方法を示しますCommunication Foundation (WCF) サービスのモデル、および WCF チャネル モデル。</span><span class="sxs-lookup"><span data-stu-id="c75b9-112">![Adapter Development icon](../../adapters-and-accelerators/adapter-oracle-database/media/44af70c9-cab1-4201-9912-d115cbc7e16f.gif "44af70c9-cab1-4201-9912-d115cbc7e16f") [Develop your Siebel applications](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md) shows you how to use the adapters with BizTalk Server, the Windows Communication Foundation (WCF) service model, and the WCF channel model.</span></span>

## <a name="messages-and-message-schemas"></a><span data-ttu-id="c75b9-113">メッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c75b9-113">Messages and message schemas</span></span>
<span data-ttu-id="c75b9-114">![チュートリアル アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/endtoendtutorials.gif "EndtoEndtutorials") [メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)メッセージ構造体と関数、レコードの種類、ポーリング操作は、その他のアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="c75b9-114">![Tutorials icon](../../adapters-and-accelerators/adapter-oracle-database/media/endtoendtutorials.gif "EndtoEndtutorials") [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) lists the message structure and actions for functions, record types, poling operations, and more.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="c75b9-115">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c75b9-115">Troubleshooting</span></span> 
<span data-ttu-id="c75b9-116">![アダプタのトラブルシューティング アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/383a7392-2eb9-485d-b6a8-0187cd5c709d.gif "383a7392-2eb9-485d-b6a8-0187cd5c709d") [Siebel アダプターのトラブルシューティングを行う](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)トレースでは、インストールをトラブルシューティングする方法を有効にする手順について説明し、パフォーマンスの問題、および例外とエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c75b9-116">![Adapter Troubleshooting icon](../../adapters-and-accelerators/adapter-oracle-database/media/383a7392-2eb9-485d-b6a8-0187cd5c709d.gif "383a7392-2eb9-485d-b6a8-0187cd5c709d") [Troubleshoot the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md) lists the steps to enable tracing, how to troubleshoot install and performance issues, and includes exception and error handling.</span></span>
