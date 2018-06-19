---
title: Microsoft BizTalk Adapter 用 mySAP Business Suite ドキュメント |Microsoft ドキュメント
description: 取得開始されると、アーキテクチャ、セキュリティ、アプリを開発、メッセージ スキーマ、および BizTalk Adapter Pack での mySAP アダプターのトラブルシューティングを行う
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26b728d7-f1e9-470a-aba5-10c9f53e2d2b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb167c3e82eace871301ca4447c6cda39874de5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217370"
---
# <a name="microsoft-biztalk-adapter-for-mysap-business-suite-documentation"></a><span data-ttu-id="ef7a2-103">Microsoft BizTalk Adapter 用 mySAP Business Suite ドキュメント</span><span class="sxs-lookup"><span data-stu-id="ef7a2-103">Microsoft BizTalk Adapter for mySAP Business Suite documentation</span></span>
<span data-ttu-id="ef7a2-104">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]さまざまなしくみを理解、アダプター、アダプターを使用して、別の接続オプションについて説明するアプリケーションを作成する方法、やアプリケーションを作成する方法を学習するのに役立つリソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef7a2-104">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] includes a variety of resources to help you understand how the adapter works, how to create applications that use the adapter, describes the different connection options, learn to create applications, and more.</span></span>

## <a name="get-started"></a><span data-ttu-id="ef7a2-105">作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="ef7a2-105">Get started</span></span>
<span data-ttu-id="ef7a2-106">![はじめにアイコン](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [BizTalk Server の概要](../../core/getting-started-with-biztalk-server.md)カスタム Rfc、機能、制限事項のインストールに関する情報が含まれています前提条件、および SAP 用データ プロバイダーの使用に関する情報。</span><span class="sxs-lookup"><span data-stu-id="ef7a2-106">![Getting started icon](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [Getting started with BizTalk Server](../../core/getting-started-with-biztalk-server.md) includes information on installing the custom RFCs, features, limitations, prerequisites, and info on using the Data Provider for SAP.</span></span>
  
## <a name="tutorials"></a><span data-ttu-id="ef7a2-107">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="ef7a2-107">Tutorials</span></span>    

<span data-ttu-id="ef7a2-108">![チュートリアル アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/endtoendtutorials.gif "EndtoEndtutorials") [SAP アダプタ チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)を使用する方法についてステップ バイ ステップのラボの説明、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]特定のシナリオです。</span><span class="sxs-lookup"><span data-stu-id="ef7a2-108">![Tutorials icon](../../adapters-and-accelerators/adapter-oracle-database/media/endtoendtutorials.gif "EndtoEndtutorials") [SAP Adapter Tutorials](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md) covers step-by-step labs to learn how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for specific scenarios.</span></span>

## <a name="architecture"></a><span data-ttu-id="ef7a2-109">Architecture</span><span class="sxs-lookup"><span data-stu-id="ef7a2-109">Architecture</span></span>  
<span data-ttu-id="ef7a2-110">![アダプター アーキテクチャ アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/4af6a1c5-948f-4bf7-bb56-4d63a47f4825.gif "4af6a1c5-948f-4bf7-bb56-4d63a47f4825") [BizTalk Server アーキテクチャ](../../core/biztalk-server-architecture.md)の概要を示します、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、および WCF です。</span><span class="sxs-lookup"><span data-stu-id="ef7a2-110">![Adapter Architecture icon](../../adapters-and-accelerators/adapter-oracle-database/media/4af6a1c5-948f-4bf7-bb56-4d63a47f4825.gif "4af6a1c5-948f-4bf7-bb56-4d63a47f4825") [BizTalk Server Architecture](../../core/biztalk-server-architecture.md) provides an overview of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], and WCF.</span></span>

## <a name="security"></a><span data-ttu-id="ef7a2-111">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ef7a2-111">Security</span></span>
<span data-ttu-id="ef7a2-112">![コミュニティ リソース アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/community.gif "コミュニティ") [、SAP アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)のベスト プラクティスと複数のアダプターを使用して、メッセージをセキュリティで保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="ef7a2-112">![Community resources icon](../../adapters-and-accelerators/adapter-oracle-database/media/community.gif "Community") [Secure your SAP applications](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md) provides best practices and more for secure your messages using the adapter.</span></span>

## <a name="developing-apps"></a><span data-ttu-id="ef7a2-113">アプリの開発</span><span class="sxs-lookup"><span data-stu-id="ef7a2-113">Developing apps</span></span>
<span data-ttu-id="ef7a2-114">![アダプター開発アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/44af70c9-cab1-4201-9912-d115cbc7e16f.gif "44af70c9-cab1-4201-9912-d115cbc7e16f") [、SAP アプリケーションの開発](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)BizTalk Server で、アダプターを使用する方法を示します、 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル、および、WCF チャネル モデル。</span><span class="sxs-lookup"><span data-stu-id="ef7a2-114">![Adapter Development icon](../../adapters-and-accelerators/adapter-oracle-database/media/44af70c9-cab1-4201-9912-d115cbc7e16f.gif "44af70c9-cab1-4201-9912-d115cbc7e16f") [Develop your SAP applications](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md) shows you how to use the adapters with BizTalk Server, the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, and the WCF channel model.</span></span>

## <a name="messages-and-message-schemas"></a><span data-ttu-id="ef7a2-115">メッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="ef7a2-115">Messages and message schemas</span></span>
<span data-ttu-id="ef7a2-116">![アダプター サンプル アイコン](../../adapters-and-accelerators/adapter-sap/media/2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a.gif "2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a") [メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)メッセージ構造体と関数では、ポーリングのレコードの種類のアクションの一覧操作、および詳細。</span><span class="sxs-lookup"><span data-stu-id="ef7a2-116">![Adapter Samples icon](../../adapters-and-accelerators/adapter-sap/media/2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a.gif "2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a") [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) lists the message structure and actions for functions, record types, poling operations, and more.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ef7a2-117">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ef7a2-117">Troubleshooting</span></span>
<span data-ttu-id="ef7a2-118">![アダプタのトラブルシューティング アイコン](../../adapters-and-accelerators/adapter-oracle-database/media/383a7392-2eb9-485d-b6a8-0187cd5c709d.gif "383a7392-2eb9-485d-b6a8-0187cd5c709d") [SAP アダプターのトラブルシューティングを行う](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)のトレースを有効にする手順し、一般的な問題を一覧表示し、解像度。</span><span class="sxs-lookup"><span data-stu-id="ef7a2-118">![Adapter Troubleshooting icon](../../adapters-and-accelerators/adapter-oracle-database/media/383a7392-2eb9-485d-b6a8-0187cd5c709d.gif "383a7392-2eb9-485d-b6a8-0187cd5c709d") [Troubleshoot the SAP adapter](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md) lists the steps to enable tracing, and lists some common issues and resolutions.</span></span> 


