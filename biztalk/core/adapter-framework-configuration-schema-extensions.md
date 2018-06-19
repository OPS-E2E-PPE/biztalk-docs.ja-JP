---
title: アダプター フレームワーク構成スキーマの拡張機能 |Microsoft ドキュメント
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
ms.openlocfilehash: 0cc50bcd592e104be0ffc82573c8ad9f4227858c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225226"
---
# <a name="adapter-framework-configuration-schema-extensions"></a>アダプター フレームワーク構成スキーマの拡張機能
BizTalk アダプター フレームワークは、XSD 定義に基づくユーザー インターフェイスの動的生成をサポートします。 アダプターは必要な XSD を提供し、アダプター フレームワークはユーザーが値を入力できるプロパティ ページを作成します。  
  
 カスタム ユーザー インターフェイスを作成するため、アダプター フレームワークでは拡張機能がいくつか提供されています。 これらの拡張機能を使用するには、アダプター フレームワーク スキーマ (BizTalkAdapterFramework.xsd) をインポートする必要があります。 スキーマをインポートすることで、修飾および特化された型にアダプター構成スキーマでアクセスして使用できます。  
  
 アダプターのプロパティ グリッドをカスタマイズするには、ここで説明する修飾タグと組み込み型を使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプター フレームワーク構成の拡張機能を有効にします。](../core/enabling-adapter-framework-configuration-extensions.md)  
  
-   [アダプター フレームワーク構成スキーマの装飾タグ](../core/adapter-framework-configuration-schema-decoration-tags.md)  
  
-   [アダプターのカスタム構成スキーマの例](../core/examples-of-custom-configuration-schemas-for-adapters.md)