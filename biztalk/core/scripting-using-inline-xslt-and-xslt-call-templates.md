---
title: インライン XSLT および XSLT 呼び出しテンプレートを使用するスクリプト |Microsoft ドキュメント
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
ms.openlocfilehash: d7c4c1d8eff582d15f9ce022053b80f2dea2f856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270434"
---
# <a name="scripting-using-inline-xslt-and-xslt-call-templates"></a>インライン XSLT および XSLT 呼び出しテンプレートを使用するスクリプト
使用するための Extensible Stylesheet Language 変換 (XSLT) スタイル シートを直接書き込むことができます、**スクリプト**functoid です。 これにより、変換を実行できます。ただし、リンクと組み込みの Functoid は、表現できない場合があります。 XSLT スクリプトの 2 種類があります: インライン XSLT および XSLT 呼び出しテンプレート。 いずれかを選択すると、**スクリプトの種類を選択して**ドロップダウン リストで、**スクリプト Functoid の構成**ダイアログ ボックスで、使用できる、サンプル コードが表示されます。  
  
 インライン XSLT スクリプトおよびインライン XSLT 呼び出しテンプレートは、外部アセンブリの関数を呼び出すことができます。 このような呼び出しを行うには、設定が必要です。、**カスタム拡張 XML**グリッドのプロパティです。 詳細については、次を参照してください。**カスタム拡張 XML (グリッド プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="inline-xslt"></a>インライン XSLT  
 インライン XSLT スクリプトでは、出力を生成することのみが可能です。 **スクリプト**functoid で、入力リンクがない可能性があります。 また、この Functoid は、送信先スキーマのレコードやフィールドに直接リンクする必要があります。  
  
 さらに、このスクリプトは、ターゲット ノードとそれに属する下部構造を作成します。  
  
 次の入力インスタンス メッセージには、連絡先に関する情報を示す 2 つの要素が含まれます。  
  
```  
<ns0:SourceInstance xmlns:ns0="http://SourceInstanceNamespace">  
    <Address>  
        <Contact>Karin Zimprich</Contact>  
        <ContactType>Referral</ContactType>  
    </Address>  
</ns0:SourceInstance>  
```  
  
 スクリプト バッファーに入力された次のインライン XSLT スクリプトの変換、**連絡先**と**ContactType**フィールドの属性をします。  
  
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
  
 このスクリプトは、前の入力インスタンス メッセージに対して実行される場合、出力スキーマが適切であると仮定して、次の出力を生成します。  
  
```  
<ns0:OutInstance xmlns:ns0="http://More_XSLT.Out">  
    <ContactInfo ContactType="Referral" Contact="Karin Zimprich" xmlns:p="http://SourceInstanceNamespace">  
    </ContactInfo>  
</ns0:OutInstance>  
```  
  
 注意してへのリンクがない場合、**スクリプト**functoid は防止しません XSLT スクリプトの入力インスタンス メッセージからデータを取得します。 このスクリプトでは、入力インスタンス値へのパスを指定します。  
  
 インライン XSLT スクリプトの別の例を参照してください。 [XML ツール (BizTalk Server Samples フォルダ)](../core/xml-tools-biztalk-server-samples-folder.md)です。  
  
## <a name="inline-xslt-call-templates"></a>インライン XSLT 呼び出しテンプレート  
 インライン XSLT スクリプトのように、インライン XSLT 呼び出しテンプレートは、送信先ノードに直接接続する必要があります。 ただし、インライン XSLT 呼び出しテンプレートでは、送信元スキーマおよび他の Functoid からのリンクを使用できます。  
  
 呼び出しテンプレートは、送信先ノードおよびそのサブ構造を作成します。  
  
 2 つの要素を連結するサンプルの XSLT 呼び出しテンプレートが表示されます、**スクリプトを入力**を選択すると、バッファー**インライン XSLT 呼び出しテンプレート**で、**スクリプトの種類を選択して**ドロップダウン リスト。  
  
 インライン XSLT 呼び出しテンプレートの別の例を参照してください。 [XML ツール (BizTalk Server Samples フォルダ)](../core/xml-tools-biztalk-server-samples-folder.md)です。  
  
## <a name="see-also"></a>参照  
 [スクリプト Functoid](../core/scripting-functoid.md)   
 [外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md)   
 [インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [スクリプト Functoid をマップに追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [スクリプト Functoid を構成する方法](../core/how-to-configure-the-scripting-functoid.md)