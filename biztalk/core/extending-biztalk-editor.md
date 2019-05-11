---
title: BizTalk エディターの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77c93ab2-0a9b-4c9d-81e5-3871fc8e6e13
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724ab7d8575a1db33654a0115530de6a259ca88e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388195"
---
# <a name="extending-biztalk-editor"></a>BizTalk エディターの拡張
BizTalk エディターは、他のインスタンス メッセージ形式をサポートする拡張機能をできるように設計されています。 実際には、XML 形式は、BizTalk エディターに組み込まれている唯一の形式です。 Microsoft に含まれている、フラット ファイル形式のサポートも[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、このような拡張機能によって追加できる機能の種類の良い例として使用されるため、BizTalk エディター拡張機能として実装されます。  
  
 一般に、BizTalk エディター拡張機能は、スキーマ ツリー内のノードに対応する XSD 要素に関連付けられている XML スキーマ定義 (XSD) 言語の注釈としてカスタム データを保存します。 ここでも、BizTalk エディターにフラット ファイル拡張子によって追加された注釈の広範なセットは、BizTalk エディターで拡張機能はスキーマにカスタム データを保存できる方法の良い例として機能します。  
  
 BizTalk エディター拡張機能には、BizTalk エディターの機能を拡張する .NET アセンブリです。 拡張機能として識別する、アセンブリの 1 つのクラスを実装する必要があります、 **IExtension**インターフェイス、および製品のインストール ディレクトリの Developer tools \schema Editor Extensions フォルダーの下にある必要があります。  
  
 拡張機能の開発者には、アセンブリで参照されている Microsoft.BizTalk.SchemaEditor.Extensibility.dll、拡張機能を BizTalk エディターを公開するために必要なすべてのインターフェイスの定義が含まれている必要があります。 これらのインターフェイスが定義されている、 **Microsoft.BizTalk.SchemaEditor.Extensibility**名前空間。  
  
 **IExtension**インターフェイスは、元の BizTalk エディターはプロパティ マネージャー、カスタム ビュー、スキーマの検証、ネイティブ インスタンスの生成、およびネイティブなどの拡張機能にアクセスする、拡張機能のエントリ ポイントインスタンスの検証。  
  
 特定のスキーマは、それに関連付けられている複数の拡張機能を持つことができます。 が、特定の時点で標準として 1 つだけを設定できます。これで設定されますが、**標準**のプロパティ、**スキーマ**ノード。 ネイティブ インスタンスの生成および検証し、スキーマ検証の使用は現在標準として設定されている拡張機能です。  
  
 拡張機能は、編集して特定のスキーマと関連付けができる、**スキーマ エディター拡張機能**のプロパティ、**スキーマ**ノード。 スキーマに関連付けられている拡張機能に関する情報が内のスキーマ自体に格納されます、**注釈**の要素、**スキーマ**要素は、次の XSD フラグメントに示すようにします。  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema11"  
        xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
        targetNamespace="http://BizTalk_Server_Project1.Schema11"  
        xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <schemaEditorExtension:schemaInfo namespaceAlias="b"  
                extensionClass="Microsoft.BizTalk.FlatFileExtension.FlatFileExtension"  
                standardName="Flat File"  
                xmlns:schemaEditorExtension="http://schemas.microsoft.com/BizTalk/2003/SchemaEditorExtensions" />  
            <b:schemaInfo schema_type="document" root_reference="Root"  
                is_receipt="no" schema_name="abc"  
                standard="Flat File"  
                count_positions_by_byte="false" />   
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="Root">  
        ...  
  
```  
  
 フレームワークが呼び出す拡張オブジェクトをインスタンス化した後、**初期化**のメソッド、 **IExtension**インターフェイスを渡して、 **ITree**オブジェクトように、拡張機能スキーマ ツリーに関する情報にアクセスできます。 たとえば、拡張機能にアクセスすることのすべての子ノードを通過でした、 **ITree.RootNode**プロパティ。  
  
 このセクションでは、BizTalk エディター拡張機能を BizTalk エディター環境に統合し、既存の BizTalk エディター コマンドにフックする方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [プロパティ マネージャー](../core/property-managers.md)  
  
-   [カスタム ビュー](../core/custom-views.md)  
  
-   [スキーマの検証](../core/schema-validation1.md)  
  
-   [インスタンスの検証](../core/instance-validation.md)  
  
-   [インスタンスの生成](../core/instance-generation.md)