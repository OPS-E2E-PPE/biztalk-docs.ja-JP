---
title: アダプター フレームワーク構成スキーマの拡張機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27c9727f-5f97-41ee-a0b8-45d90427b0af
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac88ce098f546bf97fcb2d3897f71f4e6429966f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361488"
---
# <a name="adapter-framework-configuration-schema-extensions"></a><span data-ttu-id="95130-102">アダプター フレームワーク構成スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="95130-102">Adapter Framework Configuration Schema Extensions</span></span>
<span data-ttu-id="95130-103">BizTalk アダプター フレームワークは、XSD 定義に基づいたユーザー インターフェイスの動的生成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="95130-103">The BizTalk Adapter Framework supports the dynamic generation of user interfaces based on an XSD definition.</span></span> <span data-ttu-id="95130-104">アダプターが必要な XSD を提供し、アダプター フレームワークは、値を入力するユーザーを許可するプロパティ ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="95130-104">The adapter supplies the required XSD and the Adapter Framework creates a property page that allows the user to enter values.</span></span>  
  
 <span data-ttu-id="95130-105">カスタム ユーザー インターフェイスを作成するには、アダプター フレームワークは、いくつかの拡張機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="95130-105">To create custom user interfaces, the Adapter Framework provides several extensions.</span></span> <span data-ttu-id="95130-106">これらの拡張機能を使用するには、アダプター フレームワーク スキーマ (BizTalkAdapterFramework.xsd) をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95130-106">To use these extensions, you must import the Adapter Framework schema (BizTalkAdapterFramework.xsd).</span></span> <span data-ttu-id="95130-107">スキーマをインポートすることによってにアクセスしてアダプター構成スキーマで装飾および特化された型を使用します。</span><span class="sxs-lookup"><span data-stu-id="95130-107">By importing the schema, you can access and use the decorations and specialized types in the adapter configuration schema.</span></span>  
  
 <span data-ttu-id="95130-108">装飾タグとこのセクションで説明した組み込みの型を使用すると、アダプターのプロパティ グリッドをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="95130-108">Use the decoration tags and built-in types discussed in this section to customize the property grid for an adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95130-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="95130-109">In This Section</span></span>  
  
-   [<span data-ttu-id="95130-110">アダプター フレームワーク構成の拡張機能の有効化</span><span class="sxs-lookup"><span data-stu-id="95130-110">Enabling Adapter Framework Configuration Extensions</span></span>](../core/enabling-adapter-framework-configuration-extensions.md)  
  
-   [<span data-ttu-id="95130-111">アダプター フレームワーク構成スキーマの装飾タグ</span><span class="sxs-lookup"><span data-stu-id="95130-111">Adapter Framework Configuration Schema Decoration Tags</span></span>](../core/adapter-framework-configuration-schema-decoration-tags.md)  
  
-   [<span data-ttu-id="95130-112">アダプターのカスタム構成スキーマの例</span><span class="sxs-lookup"><span data-stu-id="95130-112">Examples of Custom Configuration Schemas for Adapters</span></span>](../core/examples-of-custom-configuration-schemas-for-adapters.md)