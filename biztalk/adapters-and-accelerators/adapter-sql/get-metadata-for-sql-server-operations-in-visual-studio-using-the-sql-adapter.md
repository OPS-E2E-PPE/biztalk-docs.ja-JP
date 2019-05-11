---
title: SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7ac720-e573-4564-8d15-8212a815f1f7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35733d7d90bca30218901f145acfefc763b8ccda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369446"
---
# <a name="get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter"></a><span data-ttu-id="efb63-102">SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="efb63-102">Get metadata for SQL Server operations in Visual Studio using the SQL adapter</span></span>
<span data-ttu-id="efb63-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] 3 つ提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネント:、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="efb63-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] provides three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter—the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="efb63-104">アダプター クライアントは、これらのコンポーネントを使用して、SQL Server に接続しを実行する操作のメタデータを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb63-104">Adapter clients must use these components to connect to SQL Server and then generate metadata for the operations they want to perform.</span></span>  
  
 <span data-ttu-id="efb63-105">これらはすべて[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントで開発を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="efb63-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="efb63-106">ソリューションで使用する操作を参照および検索は、Microsoft Windows インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="efb63-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="efb63-107">これらの操作のターゲットのアダプターによって公開されているメタデータを取得しています。</span><span class="sxs-lookup"><span data-stu-id="efb63-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="efb63-108">そのメタデータを変換するには、これによって表されます Web サービス記述言語 (WSDL) ドキュメントとしてアダプターは、ソリューション (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクトの表現で使用できる形式にサービス モデル)、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="efb63-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="efb63-109">このセクションでは使用する方法について説明、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="efb63-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
