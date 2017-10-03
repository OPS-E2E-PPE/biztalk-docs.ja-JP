---
title: "PeopleSoft Enterprise の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PeopleSoft Enterprise, requirements
- send handlers, PeopleSoft requirements
- CLASSPATH environment variable
- custom component interface object
- system requirements
- GET_CI_INFO.pc
ms.assetid: fabd808d-d9b6-43b0-a12a-727189f00a9d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f267afce09e9c50d732d376fde43beaa1ef39a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="peoplesoft-enterprise-requirements"></a><span data-ttu-id="65878-102">PeopleSoft Enterprise の要件</span><span class="sxs-lookup"><span data-stu-id="65878-102">PeopleSoft Enterprise Requirements</span></span>
## <a name="send-handler-peoplesoft-requirements"></a><span data-ttu-id="65878-103">送信ハンドラー PeopleSoft の要件</span><span class="sxs-lookup"><span data-stu-id="65878-103">Send Handler PeopleSoft Requirements</span></span>  
 <span data-ttu-id="65878-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise にはカスタム コンポーネント インターフェイス (CI) が提供されているので、Java API を使用してアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="65878-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise contains a custom component interface (CI) and provides access to it through a Java API.</span></span> <span data-ttu-id="65878-105">PeopleSoft ツールを使用して PeopleSoft システムにカスタム CI オブジェクトの `GET_CI_INFO` を配置し、BizTalk Adapter for PeopleSoft Enterprise に必要なメタデータ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="65878-105">A custom CI object, `GET_CI_INFO`, is deployed in the PeopleSoft system using PeopleSoft Tools to provide metadata information that is required by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="65878-106">詳細については、次を参照してください。[を使用して PeopleSoft Enterprise に準備](../core/preparing-to-use-peoplesoft-enterprise.md)です。</span><span class="sxs-lookup"><span data-stu-id="65878-106">For more information, see [Preparing to Use PeopleSoft Enterprise](../core/preparing-to-use-peoplesoft-enterprise.md).</span></span>  
  
 <span data-ttu-id="65878-107">1 回は、カスタム コンポーネント インターフェイスをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="65878-107">Uploading the custom component interface is a one-time occurrence.</span></span> <span data-ttu-id="65878-108">この `GET_CI_INFO.pc` ファイルで製品をインストールします。アダプターで CI を参照するには、このファイルがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65878-108">This file, `GET_CI_INFO.pc`, installs with the product and must be installed before you can use the adapter to browse CIs.</span></span> <span data-ttu-id="65878-109">PeopleSoft Application Designer にアクセスできる必要がありますが、BizTalk Server コンピューター上に Application Designer アプリケーションが存在している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="65878-109">You must have access to the PeopleSoft Application Designer, but the Application Designer application does not have to be on the BizTalk Server computer.</span></span> <span data-ttu-id="65878-110">Application Designer を使用して、参照する PeopleSoft コンピューターにカスタム CI をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="65878-110">You use the Application Designer to upload the custom CI onto the PeopleSoft computer that you browse.</span></span>  
  
 <span data-ttu-id="65878-111">環境変数 CLASSPATH を設定する必要がありますのでから PeopleSoft コンピューターにアクセスする必要があります (情報を設定または、**トランスポートのプロパティ**画面) を PeopleSoft の指す`PSJOA/psjoa.jar`ファイル。</span><span class="sxs-lookup"><span data-stu-id="65878-111">You must have access to the PeopleSoft computer because you must set the environment variable CLASSPATH (or set the information in the **Transport Properties** screen) to point to PeopleSoft's `PSJOA/psjoa.jar` file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65878-112">参照</span><span class="sxs-lookup"><span data-stu-id="65878-112">See Also</span></span>  
 <span data-ttu-id="65878-113">[作業の開始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="65878-113">[Getting Started](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span></span>  
 [<span data-ttu-id="65878-114">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="65878-114">Planning and Architecture</span></span>](../core/planning-and-architecture13.md)