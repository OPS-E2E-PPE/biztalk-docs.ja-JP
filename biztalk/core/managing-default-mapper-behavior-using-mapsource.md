---
title: 既定のマッパーを使用して動作を管理する&lt;mapsource&gt; |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deea839c-e52e-44c6-ac0d-4396dc5b10d8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7b4173d514fcc7c671cfd367f64dfc2726bba72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329500"
---
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a>既定のマッパーを使用して動作を管理する&lt;mapsource&gt;
BizTalk マッパーの特定の既定動作を変更するには、属性を変更、 **mapsource**直接マップ ソース (.btm) ファイル内の要素。  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a>値のマッピング Functoid のコード生成の最適化  
 マッパーが XSLT を呼び出すコードを生成するとき、**値のマッピング**functoid、変数を使用して、結果を格納します。 使用することができます、 **OptimizeValueMapping**フラグを最適化するために、**値のマッピング**functoid 変数が生成されるように場合にのみ、`if`ステートメントの評価が`True`します。 たとえば、 **OptimizeValueMapping**設定**いいえ**:  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 このコードを移動することによって最適化できます、**値のマッピング**functoid の呼び出しの本文に、`if`ステートメントでは、呼び出しは、必要なは場合のみが行われることを確認します。 設定**OptimizeValueMapping**に**はい**次のコードを生成できます。  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 マッパーは、この最適化自動的に設定した場合、 **OptimizeValueMapping**の属性、 **mapsource**要素をマップ ソース (.btm) ファイル**はい**として表示されます。  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a>大きな容量を使用するスキーマ  
 時、マッパーを使用してを深く複雑な構造体や、再帰的なノードのフット プリントが非常に大きなインスタンスを持つスキーマ、マップのテスト、検証、またはマップのコンパイルに時間がかかる場合がありますか、最悪の場合、「メモリ不足」エラーが発生します。 これは、小規模で複雑なスキーマおよびサイズの大きいスキーマに発生する可能性があります。  
  
 複雑なスキーマの問題は、マッパーが再帰的に読み込む全体のスキーマ ツリーをノードに接続しているリンクがあるか、またはを調べてという事実が原因、**値**プロパティを設定します。 設定してこの問題を軽減することができます、 **GenerateDefaultFixedNodes**のフラグ、 **mapsource**に .btm ファイル内の要素**いいえ**よう。  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 この設定で、マッパーはターゲット スキーマの各スキーマのノードに関連付けられた内部コンパイラ ノードを作成するには必要ありません。 コンパイラによってアカウントにリンクされたノードだけが取得されます。 これが大幅にメモリ消費量が減少し、「マップのテスト」または「マップの検証」操作をマップのコンパイルや保存を行う場合、処理速度が向上します。  
  
 ただし、ときに、 **GenerateDefaultFixedNodes**にフラグが設定されている**いいえ**、ターゲット スキーマの設定フィールドの既定値は、マップによって生成されたインスタンスで保持されません。 これは、これらの値が対象のインスタンスに必要な場合の問題です。 必要な値でもう一度設定する必要がこれを回避する、マップで明示的にします。 設定することができます、 **GenerateDefaultFixedNodes**フラグを**RequiredDefaults**、すべての必須ノードを考慮することを意味します。 これは、リンクされたノード、ノードが既定値のノード、 **MinOccurs**プロパティをより大きいまたは 1、および親が必要なノードと等しく設定します。  
  
> [!NOTE]
>  設定した後**GenerateDefaultFixedNodes**に**いいえ**または**RequiredDefaults**、マップをテストし、出力が場合と同じことを確認する必要があります**GenerateDefaultFixedNodes**の既定値に設定されている**はい**がすべてのノードが考慮コンパイラでします。  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a>For-each ループ、条件、使用率を管理して、値のマッピング Functoid  
 使用すると、**ループ**functoid、**条件付き**functoid、または**値のマッピング**functoid、`xsl:for-each`ステートメントがコンパイルされたマップで生成されます。 送信先スキーマの子フィールドに無制限の最大出現回数、`xsl:for-each`ステートメントは、子フィールドに配置されます。 子フィールドには、最大出現回数を無制限にいない場合、`xsl:for-each`ステートメントは、子フィールドの親フィールドに配置されます。  
  
 ただし、ための場所、`xsl:for-each`ステートメントが、マップの結果に影響することができます、 `xsl:for-each` に子フィールドの最大出現回数を設定するかどうかに関係なく、送信先スキーマの子フィールドに配置するステートメント**1**します。  
  
 配置を制御することができます、`xsl:for-each`ステートメントの値を変更することによって、 **TreatElementsAsRecords**マップ (.btm) ファイルに示すように属性します。  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 この属性を設定すると**はい**、`xsl:for-each`ステートメントに、子フィールドの最大出現回数を設定するかどうかに関係なく、送信先スキーマの子フィールドに配置されます**1**します。  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a>繰り返されるシーケンス グループをマップするときに、順序を維持  
 XSD スキーマ内のシーケンス グループは、メッセージ インスタンスで表されないため、ループ コンテキストを提供しません。 シーケンス グループで可能性をループなし、マッパーのコンパイラは、セグメントの順序を維持するために適切な XSLT を生成しません。 その結果、入力インスタンスに存在する相対コンテキストが失われ、さらに処理する役に立たなく出力インスタンスは、相対コンテキストによって異なります。  
  
 使用することができます、 **PreserveSequenceOrder**繰り返しをマッピングするときに、レコードの順序を維持するためにフラグが別の繰り返されるシーケンスをシーケンス処理します。 フラグの値の設定既定では、**いいえ**以前で作成された既存のマップの機能を保持するために[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バージョン フラグが存在しません。 を新しく作成されたマップで、フラグが存在するその値を設定して**いいえ**します。 セグメントの順序を維持する必要があります明示的に設定する値**はい**で示すように .btm ファイル。  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 サンプルの入力インスタンスを次に示します。  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 **PreserveSequenceOrder**フラグに設定**いいえ**、出力インスタンスは、次のようになります。  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 **PreserveSequenceOrder**フラグを設定**はい**、出力インスタンスは、次のようになります。  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)