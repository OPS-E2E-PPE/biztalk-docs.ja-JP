---
title: スキーマのカテゴリ、アダプター メタデータのウィザードの追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3927c676-f60a-449e-be43-6f75e28aefe1
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fda24ee5ef4993c90eb82e0f406da2e06618776
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271506"
---
# <a name="schema-categories-in-the-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードのスキーマ カテゴリ

## <a name="overview"></a>概要
> [!NOTE]
>  このトピックは、実装する静的アダプターに対してのみ、 **IStaticAdapterConfig**インターフェイスです。  
  
 アダプターは、データを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に渡す前に、数千あるスキーマのうちのいずれかを使用してデータを変換します。 メタデータを BizTalk プロジェクトに追加する場合は、アダプター メタデータの追加ウィザードを使用して、アダプターと連携するすべてのスキーマの一覧からスキーマを選択します。  
  
 サンプル ファイル アダプターの CategorySchema.xml ファイルは、サービス スキーマのツリー ビュー構成を生成するために、アダプター フレームワークの BiztalkAdapterFramework.xsd ファイルと共に使用されるスキーマ インスタンスです。  BizTalkAdapterFramework.xsd ファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools フォルダーにあります。  
  
 このファイルを作成し、ソリューションに即した方法でスキーマを構成できるようにする必要があります。 CategorySchema.xml の既存のカテゴリは、独自のツリーで実行できることの一例にすぎません。 これらのカテゴリとサンプル アダプターによって渡されるデータは特に関連性がありません。 スキーマの構成は、数千もの異なるスキーマを利用できるアプリケーション固有のアダプターで特に重要になります。 トランスポート固有のアダプターの場合、ツリー ビュー構成は必要ありません。  
  
 次の図に示しています、 **インポートするサービス**アダプター メタデータの追加ウィザードのページです。  
  
 ![](../core/media/ebiz-prog-custad-tree.gif "ebiz_prog_custad_tree")  
アダプター メタデータの追加ウィザードのスキーマ カテゴリのツリー ビュー  


## <a name="sample-xml"></a>サンプル XML
  
 CategorySchema.xml ファイルのコードを次に示します。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<CategoryTree>  
     <DisplayName>Services Organization</DisplayName>  
     <DisplayDescription>An organization of application services</DisplayDescription>  
     <CategoryTreeNode>  
          <DisplayName>Health Care</DisplayName>  
          <Description>Services under Health Care</Description>  
          <CategoryTreeNode>  
               <DisplayName>Administrative</DisplayName>  
               <Description>Administrative Health Care Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Eligibility</DisplayName>  
                    <Description>Eligibility Verification Transactions</Description>  
                    <WSDLReference>ANSI X 12 270</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
     <CategoryTreeNode>  
          <DisplayName>Manufacturing</DisplayName>  
          <Description>Manufacturing Services</Description>  
          <CategoryTreeNode>  
               <DisplayName>Inventory</DisplayName>  
               <Description>Inventory Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Requisition</DisplayName>  
                    <Description>Requisition</Description>  
                    <WSDLReference>RequisitionService</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
</CategoryTree>  
```  
  
 このスキーマ インスタンスには、次のノード タイプが表示されます。  
  
-   **CategoryTree です。** システム情報モデルの最上位レベルの構造。 0 個以上の CategoryTreeNode ノード、ExpandableCategoryTreeNode ノード、および ServiceTreeNode ノードが格納されます。  
  
-   **CategoryTreeNode です。** 0 個以上の CategoryTreeNode ノード、および ServiceTreeNode ノードが格納されます。 ユーザー インターフェイスでフォルダーとして表示される CategoryTreeNode を使用して、関連する一連のサービスをグループ化します。 通常、このノードには、表示されるサービスの表示名と説明が格納されます。 子ノードの数が少数である場合、アダプターは CategoryTreeNode を使用する可能性があります。  
  
-   **ExpandableCategoryTreeNode です。** 展開時に動的に生成されるリーフ ノード。 ExpandableCategoryTreeNode はプレースホルダーとして使用され、UI でフォルダーとして表示されます。 このノードを使用すると、ユーザーがノードをクリックして展開するまで、サブ要素を含むカテゴリ ノードの生成を延期することができます。 多数の子ノードがカテゴリに含まれる場合、アダプターは ExpandableCategoryTreeNode を使用する可能性があります。  
  
-   **ServiceTreeNode です。** ServiceTreeNode は、UI でドキュメントまたはリーフ ノードとして表示され、Web Services Description Language (WSDL) ファイルを表します。  
  
 ユーザーは、ノードを展開するフォルダーをクリックすると、アダプター フレームワークは、 **IStaticAdapterConfig.GetServiceOrganization**メソッドの値として、ノードの名前を渡すアダプターを**NodeIdentifier**属性。 アダプターは、ExpandableCategoryTreeNode の下に追加するサブノードを含む CategoryTree を返す必要があります。 アダプター フレームワークは、ExpandableCategoryTreeNode を CategoryTreeNode に置き換えて、返された CategoryTree の子を CategoryTreeNode に追加します。  
  
> [!NOTE]
>  最初の呼び出しで**IStaticAdapterConfig.GetServiceOrganization**アダプター フレームワーク ノード識別子に対して null を渡します。 これは、ルート レベルの CategoryTree を返すようにアダプターに通知します。  
  
 BiztalkAdapterFramework.xsd ファイルから抽出したカテゴリ ツリー スキーマを次に示します。 アダプター メタデータの追加ウィザードは、このカテゴリ ツリー スキーマをスケルトン ツリーとして使用し、特定のアプリケーション依存エンティティを XML ファイルから生成します。 この例では、CategorySchema.xml ファイルがその XML ファイルに該当します。  
  
```  
<!-- Service Organization Tree schema used by Add Adapter Wizard -->  
    <xs:element name="CategoryTree" type="CategoryTree" />  
    <xs:complexType name="CategoryTree">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="DisplayDescription" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ExpandableCategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
        </xs:sequence>  
        <xs:attribute name="NodeIdentifier" type="xs:string" use="required"></xs:attribute>  
    </xs:complexType>  
    <xs:complexType name="CategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ServiceTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:element name="WSDLReference" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:schema>  
```  
  
 CategorySchema.xml ファイルを修正したら、AdapterManagement プロジェクトをリビルドし、アダプター メタデータの追加ウィザードを実行して、CategorySchema.xml のツリーが正しく表示されることを確認します。  
  
 アダプター メタデータの追加ウィザードを実行する方法の詳細については、次を参照してください。、**アダプター メタデータのウィザード ダイアログ ボックスを追加**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。