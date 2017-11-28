---
title: "PeopleSoft Enterprise アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BizTalk Adapter for PeopleSoft Enterprise
ms.assetid: 6c3dd7fd-3566-4063-a2fd-2acbe64d2885
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41b40c57ad3defcc7fa390e76303ec2b4e6bd291
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="peoplesoft-enterprise-adapter"></a><span data-ttu-id="049cf-102">PeopleSoft Enterprise アダプタ</span><span class="sxs-lookup"><span data-stu-id="049cf-102">PeopleSoft Enterprise Adapter</span></span>
<span data-ttu-id="049cf-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise により、PeopleSoft オブジェクトを利用することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="049cf-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise enables you to use PeopleSoft objects.</span></span> <span data-ttu-id="049cf-104">このドキュメントでは、アダプターをセットアップして PeopleSoft 固有の情報にアクセスする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="049cf-104">This documentation discusses setting up the adapter to access PeopleSoft-specific information.</span></span>  
  
 <span data-ttu-id="049cf-105">次の表は、主要なトピックへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="049cf-105">The following table provides links to key topics.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="049cf-106">作業の開始</span><span class="sxs-lookup"><span data-stu-id="049cf-106">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)<br /><br /> [<span data-ttu-id="049cf-107">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="049cf-107">Planning and Architecture</span></span>](../core/planning-and-architecture13.md)<br /><br /> [<span data-ttu-id="049cf-108">BizTalk Adapter for PeopleSoft Enterprise のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="049cf-108">Security in BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)<br /><br /> [<span data-ttu-id="049cf-109">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="049cf-109">Developing Applications</span></span>](../core/developing-applications4.md)<br /><br /> [<span data-ttu-id="049cf-110">BizTalk Adapter for PeopleSoft Enterprise の展開</span><span class="sxs-lookup"><span data-stu-id="049cf-110">Deploying BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)<br /><br /> [<span data-ttu-id="049cf-111">BizTalk Adapter for PeopleSoft Enterprise の管理</span><span class="sxs-lookup"><span data-stu-id="049cf-111">Administering BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/administering-biztalk-adapter-for-peoplesoft-enterprise.md)<br /><br /> [<span data-ttu-id="049cf-112">PeopleSoft のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="049cf-112">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)<br /><br /> [<span data-ttu-id="049cf-113">PeopleSoft Enterprise のテクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="049cf-113">Technical Reference for PeopleSoft Enterprise</span></span>](../core/technical-reference-for-peoplesoft-enterprise.md)|[<span data-ttu-id="049cf-114">付録 a: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="049cf-114">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)<br /><br /> [<span data-ttu-id="049cf-115">付録 b: PeopleSoft アプリケーションの使用</span><span class="sxs-lookup"><span data-stu-id="049cf-115">Appendix B: Using the PeopleSoft Application</span></span>](../core/appendix-b-using-the-peoplesoft-application.md)<br /><br /> [<span data-ttu-id="049cf-116">付録 c: コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="049cf-116">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)<br /><br /> [<span data-ttu-id="049cf-117">BizTalk Adapter for PeopleSoft Enterprise の UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="049cf-117">UI Reference for BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)|