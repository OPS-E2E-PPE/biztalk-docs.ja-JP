---
title: BizTalk エディターを拡張 |Microsoft ドキュメント
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
ms.openlocfilehash: 8f8e4f574e652420ae11410e52268a199639cf6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246242"
---
# <a name="extending-biztalk-editor"></a>BizTalk エディターの拡張
BizTalk エディターの機能を拡張して、他のインスタンス メッセージ形式をサポートすることができます。 実際には、XML 形式は、BizTalk エディターに組み込まれている唯一の形式です。 ただし、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に含まれるフラット ファイル形式のサポートも、BizTalk エディターの拡張機能として実装されます。これは、拡張機能によって追加できる機能の代表的な例です。  
  
 通常、BizTalk エディターの拡張機能は、スキーマ ツリーのノードに対応する XSD 要素に関連付けられている XSD (XML Schema Definition) 言語の注釈として、カスタム データを保存します。 また、フラット ファイル拡張機能によって BizTalk エディターに追加される数多くの注釈のセットは、BizTalk エディターの拡張機能スキーマにカスタム データを保存する方法を示す代表的な例といえます。  
  
 BizTalk エディターの拡張機能は、BizTalk エディターの機能を拡張する .NET アセンブリです。 拡張機能として識別する、アセンブリの 1 つのクラスを実装する必要があります、 **IExtension**インターフェイス、および製品のインストール ディレクトリの Developer tools \schema Editor Extensions フォルダーの下にある必要があります。  
  
 拡張機能の開発者は、拡張機能を BizTalk エディターに公開するために必要なすべてのインターフェイスの定義が格納されている Microsoft.BizTalk.SchemaEditor.Extensibility.dll を、アセンブリで参照する必要があります。 これらのインターフェイスが定義されている、 **Microsoft.BizTalk.SchemaEditor.Extensibility**名前空間。  
  
 **IExtension**インターフェイスは、BizTalk エディター元となるプロパティ マネージャー、カスタム ビュー、スキーマの検証、ネイティブ インスタンスの生成、およびネイティブなど、拡張機能にアクセスする、拡張機能のエントリ ポイントインスタンスの検証。  
  
 特定のスキーマに関連付けられている複数の拡張子を持つことができます。 が、特定の時点で、標準として 1 つだけを設定できます。この設定は、**標準**のプロパティ、**スキーマ**ノード。 現在、標準設定として使用できる拡張機能は、ネイティブ インスタンスの生成や検証に使用される機能、およびスキーマ検証に使用される機能です。  
  
 拡張機能を関連付ける特定のスキーマを編集して、**スキーマ エディター拡張機能**のプロパティ、**スキーマ**ノード。 スキーマに関連付けられている拡張機能に関する情報はスキーマ自体内で、**注釈**の要素、**スキーマ**要素は、次の XSD フラグメントに示すようにします。  
  
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
  
 フレームワークを呼び出す拡張オブジェクトをインスタンス化した後、**初期化**のメソッド、 **IExtension**インターフェイスを渡して、 **ITree**オブジェクトように拡張機能スキーマ ツリーに関する情報にアクセスできます。 たとえば、拡張機能は、アクセスすることでのすべての子ノードを通過でした、 **ITree.RootNode**プロパティです。  
  
 このセクションでは、BizTalk エディターの拡張機能を BizTalk エディター環境に統合して、既存の BizTalk エディター コマンドにフックする方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [プロパティ マネージャー](../core/property-managers.md)  
  
-   [カスタム ビュー](../core/custom-views.md)  
  
-   [スキーマの検証](../core/schema-validation1.md)  
  
-   [インスタンスの検証](../core/instance-validation.md)  
  
-   [インスタンスの生成](../core/instance-generation.md)