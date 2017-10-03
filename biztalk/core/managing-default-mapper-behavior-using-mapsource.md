---
title: "既定のマッパーを使用して動作を管理する&lt;mapsource&gt; |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: deea839c-e52e-44c6-ac0d-4396dc5b10d8
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44e2e66350709c6b857d875ec3979fe3f7059648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a>既定のマッパーを使用して動作を管理する&lt;mapsource&gt;
BizTalk マッパーの特定の既定動作を変更するにはの属性を変更することによって、 **mapsource**直接マップ ソース (.btm) ファイル内の要素。  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a>値のマッピング Functoid のコード生成の最適化  
 マッパーが XSLT を呼び出すコードを生成するとき、**値のマッピング**functoid は、変数は、結果を格納するために使用します。 使用することができます、 **OptimizeValueMapping**フラグを最適化するために、**値のマッピング**functoid 変数が生成されるようされる場合にのみ、`if`ステートメントの評価が`True`です。 たとえば、 **OptimizeValueMapping** 'éý'**いいえ**:  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 このコードを移動することによって最適化でした、**値のマッピング**の本体に functoid の呼び出し、`if`ステートメントでは、呼び出しのだけことが必要な場合に発生することを確認します。 設定**OptimizeValueMapping**に**はい**次のコードが生成されます。  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 マッパーは、この最適化自動的に設定した場合、 **OptimizeValueMapping**の属性、 **mapsource**マップ ソース (.btm) ファイル内の要素**はい**として表示されます。  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a>大きな容量を使用するスキーマの調整  
 構造が非常に複雑で容量の大きいスキーマをマッパーが使用している場合は、マップのテスト、マップの検証、またはマップのコンパイルに時間がかかり、最悪の場合、"メモリの不足です" エラーが発生する可能性があります。 これは、小規模で複雑なスキーマ、およびサイズの大きいスキーマでに発生する可能性があります。  
  
 複雑なスキーマで問題が生じることは、マッパーが再帰的に読み込み、スキーマ全体のツリー ノードに接続しているリンクがあるかを探すため、**値**プロパティが設定されます。 この問題を軽減するには、設定、 **GenerateDefaultFixedNodes**のフラグを設定、 **mapsource**に .btm ファイル内の要素**なし**ように。  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 この設定を使用すると、マッパーはターゲット スキーマの各スキーマ ノードに関連付けられた内部のコンパイラ ノードを作成する必要がなくなります。 コンパイラでは、リンクされたノードだけが考慮されます。 これにより、メモリの使用量が大幅に削減され、"マップのテスト" 操作や "マップの検証" 操作を実行したり、マップのコンパイルや保存を行うときに、処理が高速化されます。  
  
 ただし、ときに、 **GenerateDefaultFixedNodes**にフラグが設定されている**いいえ**、ターゲット スキーマに設定する既定のフィールド値は、マップによって生成されたインスタンスでは保持されません。 これは、これらの値がターゲット インスタンス内で必要である場合問題になります。 この問題を回避するには、必要な値をマップ内で明示的に設定し直す必要があります。 設定することができます、 **GenerateDefaultFixedNodes**フラグを**RequiredDefaults**、すべての必須ノードを考慮することを意味します。 これは、リンクされたノードがについて説明、既定値がノード値のノード、 **MinOccurs**に以上の値を 1 つ、およびノードの親が必要なプロパティが設定されます。  
  
> [!NOTE]
>  設定した後**GenerateDefaultFixedNodes**に**いいえ**または**RequiredDefaults**、マップをテストし、出力が場合と同じであることを確認する必要があります**GenerateDefaultFixedNodes**の既定値に設定されている**はい**、するすべてのノードが考慮コンパイラによってにします。  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a>ループ Functoid、条件付き Functoid、および値のマッピング Functoid と for-each の使用の管理  
 使用する場合、**ループ**functoid、**条件付き**functoid、または**値のマッピング**functoid、`xsl:for-each`ステートメントがコンパイルされたマップで生成されます。 マップ先スキーマの子フィールドの最大出現回数が "バインド解除済み" である場合、`xsl:for-each` ステートメントは子フィールドに配置されます。 子フィールドの最大出現回数が "バインド解除済み" でない場合、`xsl:for-each` ステートメントはその子フィールドの親フィールドに配置されます。  
  
 ただし、ための場所、`xsl:for-each`ステートメントがマップの結果に影響する可能性があります、 `xsl:for-each` に子フィールドの最大出現回数を設定するかどうかに関係なく、送信先スキーマの子フィールドに配置するステートメント**1**です。  
  
 配置を制御することができます、`xsl:for-each`ステートメントの値を変更することによって、 **TreatElementsAsRecords**ように、マップ (.btm) ファイルに属性します。  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 この属性を設定すると**はい**、`xsl:for-each`ステートメントは、子フィールドの最大出現回数に設定されているかどうかに関係なく、送信先スキーマの子フィールドに配置**1**です。  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a>繰り返されるシーケンス グループをマップする順序の保持  
 XSD スキーマ内のシーケンス グループは、メッセージ インスタンスで表現できないため、ループ コンテキストを提供しません。 シーケンス グループでループを実現できないので、マッパーのコンパイラではセグメントの順序を維持するための適切な XSLT が生成されません。 その結果、入力インスタンスに存在する相対コンテキストが失われ、以降、相対コンテキストに依存する処理では出力インスタンスが役に立たなくなります。  
  
 使用することができます、 **PreserveSequenceOrder**繰り返しをマップするときに、レコードの順序を維持するためにフラグが別の繰り返しシーケンス順序。 既定では、フラグの値に設定**いいえ**以前で作成された既存のマップの機能を保持するために[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]フラグが存在しないバージョンです。 新しく作成されたマップでフラグが存在するその値を設定して**いいえ**です。 セグメントの順序を維持する必要があります明示的に設定する値**はい**ように、.btm ファイルで。  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 以下に、サンプルの入力インスタンスを示します。  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 **PreserveSequenceOrder**フラグに設定されて**いいえ**、出力インスタンスは、次のようになります。  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 **PreserveSequenceOrder**フラグに設定**はい**、出力インスタンスは、次のようになります。  
  
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