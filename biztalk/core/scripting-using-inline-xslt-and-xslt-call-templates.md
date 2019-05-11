---
title: インライン XSLT および XSLT 呼び出しテンプレートを使用したスクリプト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3168417-3653-4c9e-a09c-184ffdc0ccb2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5df34bc134b9cb842d4ebc0db96f00a3716ee5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251244"
---
# <a name="scripting-using-inline-xslt-and-xslt-call-templates"></a>使用してインライン XSLT および XSLT 呼び出しテンプレート スクリプト
使用するための拡張可能なスタイル シート言語変換 (XSLT) スタイル シートを直接書き込むことができます、 **Scripting** functoid。 これは、ようにリンクするには、変換を実行して組み込みの functoid で表すされない場合があります。 XSLT スクリプトの 2 種類があります。 インライン XSLT および XSLT 呼び出しテンプレート。 いずれかを選択すると、**スクリプトの種類を選択します。**  ドロップダウン ボックスで、**スクリプト Functoid の構成**ダイアログ ボックスで、使用できる、サンプル コードが表示されます。  
  
 インライン XSLT スクリプトおよびインライン XSLT 呼び出しテンプレートは、外部アセンブリ内の関数を呼び出すことがあります。 このような呼び出しを行うには、設定が必要です。、**カスタム拡張 XML**グリッドのプロパティ。 詳細については、次を参照してください。**カスタム拡張 XML (グリッド プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="inline-xslt"></a>インライン XSLT  
 インライン XSLT スクリプトは、出力を生成することのみです。 **Scripting** functoid は、入力リンクがありません。 Functoid は、レコードまたはフィールドを送信先スキーマにも直接リンクする必要があります。  
  
 さらに、スクリプトは、ターゲット ノードとその下にある構造体の作成を担当します。  
  
 次の入力インスタンス メッセージには、連絡先情報を表す 2 つの要素が含まれています。  
  
```  
<ns0:SourceInstance xmlns:ns0="http://SourceInstanceNamespace">  
    <Address>  
        <Contact>Karin Zimprich</Contact>  
        <ContactType>Referral</ContactType>  
    </Address>  
</ns0:SourceInstance>  
```  
  
 スクリプト バッファーに入力された次のインライン XSLT スクリプトに変換、**連絡先**と**ContactType**フィールドが属性。  
  
```  
<ContactInfo xmlns:p="http://SourceInstanceNamespace">  
     <xsl:variable name="var:var1" select="/p:SourceInstance/Address/ContactType" />  
     <xsl:attribute name="ContactType">  
          <xsl:value-of select="$var:var1" />  
     </xsl:attribute>  
     <xsl:variable name="var:var2" select="/p:SourceInstance/Address/Contact" />  
     <xsl:attribute name="Contact">  
          <xsl:value-of select="$var:var2" />  
     </xsl:attribute>  
</ContactInfo>  
```  
  
 スクリプトでは、上記の入力インスタンス メッセージに対して実行すると、適切な出力スキーマと仮定すると、次の出力を生成します。  
  
```  
<ns0:OutInstance xmlns:ns0="http://More_XSLT.Out">  
    <ContactInfo ContactType="Referral" Contact="Karin Zimprich" xmlns:p="http://SourceInstanceNamespace">  
    </ContactInfo>  
</ns0:OutInstance>  
```  
  
 注意へのリンクがない場合、 **Scripting** functoid は、入力インスタンス メッセージからのデータの取得から XSLT スクリプトを妨げません。 スクリプトでは、入力インスタンス値へのパスを指定します。  
  
 インライン XSLT スクリプトの別の例を参照してください。 [XML ツール (BizTalk Server Samples フォルダー)](../core/xml-tools-biztalk-server-samples-folder.md)します。  
  
## <a name="inline-xslt-call-templates"></a>インライン XSLT 呼び出しテンプレート  
 インライン XSLT スクリプトのように、インライン XSLT 呼び出しテンプレートは、移動先のノードに直接接続する必要があります。 ただし、インライン XSLT 呼び出しテンプレートは、送信元スキーマおよびその他の functoid からのリンクを使用することがあります。  
  
 呼び出しテンプレートは、送信先ノードおよびそのサブ構造を作成するためです。  
  
 2 つの要素を連結するサンプルの XSLT 呼び出しテンプレートが表示されます、**スクリプトの入力**を選択するとバッファー**インライン XSLT 呼び出しテンプレート**で、**スクリプトの種類を選択します**。ドロップダウン リスト。  
  
 インライン XSLT 呼び出しテンプレートの別の例を参照してください。 [XML ツール (BizTalk Server Samples フォルダー)](../core/xml-tools-biztalk-server-samples-folder.md)します。  
  
## <a name="see-also"></a>参照  
 [スクリプト Functoid](../core/scripting-functoid.md)   
 [外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md)   
 [インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [マップにスクリプト Functoid を追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [スクリプト Functoid の構成方法](../core/how-to-configure-the-scripting-functoid.md)