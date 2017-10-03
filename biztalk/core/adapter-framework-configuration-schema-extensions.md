---
title: "アダプター フレームワーク構成スキーマの拡張機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27c9727f-5f97-41ee-a0b8-45d90427b0af
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cc50bcd592e104be0ffc82573c8ad9f4227858c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-framework-configuration-schema-extensions"></a><span data-ttu-id="90822-102">アダプター フレームワーク構成スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="90822-102">Adapter Framework Configuration Schema Extensions</span></span>
<span data-ttu-id="90822-103">BizTalk アダプター フレームワークは、XSD 定義に基づくユーザー インターフェイスの動的生成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="90822-103">The BizTalk Adapter Framework supports the dynamic generation of user interfaces based on an XSD definition.</span></span> <span data-ttu-id="90822-104">アダプターは必要な XSD を提供し、アダプター フレームワークはユーザーが値を入力できるプロパティ ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="90822-104">The adapter supplies the required XSD and the Adapter Framework creates a property page that allows the user to enter values.</span></span>  
  
 <span data-ttu-id="90822-105">カスタム ユーザー インターフェイスを作成するため、アダプター フレームワークでは拡張機能がいくつか提供されています。</span><span class="sxs-lookup"><span data-stu-id="90822-105">To create custom user interfaces, the Adapter Framework provides several extensions.</span></span> <span data-ttu-id="90822-106">これらの拡張機能を使用するには、アダプター フレームワーク スキーマ (BizTalkAdapterFramework.xsd) をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90822-106">To use these extensions, you must import the Adapter Framework schema (BizTalkAdapterFramework.xsd).</span></span> <span data-ttu-id="90822-107">スキーマをインポートすることで、修飾および特化された型にアダプター構成スキーマでアクセスして使用できます。</span><span class="sxs-lookup"><span data-stu-id="90822-107">By importing the schema, you can access and use the decorations and specialized types in the adapter configuration schema.</span></span>  
  
 <span data-ttu-id="90822-108">アダプターのプロパティ グリッドをカスタマイズするには、ここで説明する修飾タグと組み込み型を使用します。</span><span class="sxs-lookup"><span data-stu-id="90822-108">Use the decoration tags and built-in types discussed in this section to customize the property grid for an adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90822-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="90822-109">In This Section</span></span>  
  
-   [<span data-ttu-id="90822-110">アダプター フレームワーク構成の拡張機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="90822-110">Enabling Adapter Framework Configuration Extensions</span></span>](../core/enabling-adapter-framework-configuration-extensions.md)  
  
-   [<span data-ttu-id="90822-111">アダプター フレームワーク構成スキーマの装飾タグ</span><span class="sxs-lookup"><span data-stu-id="90822-111">Adapter Framework Configuration Schema Decoration Tags</span></span>](../core/adapter-framework-configuration-schema-decoration-tags.md)  
  
-   [<span data-ttu-id="90822-112">アダプターのカスタム構成スキーマの例</span><span class="sxs-lookup"><span data-stu-id="90822-112">Examples of Custom Configuration Schemas for Adapters</span></span>](../core/examples-of-custom-configuration-schemas-for-adapters.md)