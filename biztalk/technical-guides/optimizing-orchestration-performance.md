---
title: オーケストレーション パフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 437c7325-f037-451a-8dbd-f8d8c8889e20
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 473c6e904def7f58adcb52eb26e46891be9c41d0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971883"
---
# <a name="optimizing-orchestration-performance"></a>オーケストレーション パフォーマンスの最適化
このトピックでは、オーケストレーションを BizTalk Server ソリューションで使用するためのベスト プラクティスについて説明します。 これには、推奨事項が含まれます。  
  
-   オーケストレーションを使用して BizTalk Server ソリューションの遅延時間の短縮  
  
    -   メッセージングのみのパターンのオーケストレーションを排除  
  
    -   オーケストレーションから送信インラインを利用します。  
  
    -   オーケストレーションの永続化ポイントを最小限に抑える  
  
-   オーケストレーションを入れ子  
  
-   オーケストレーションのデザイン パターン  
  
-   オーケストレーションの例外処理ブロック  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a>低待機時間シナリオのオーケストレーションを最適化するための推奨事項  
 オーケストレーションを使用して BizTalk Server ソリューションの待機時間を短縮する、次の手法を使用できます。  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a>メッセージングのみのパターンのオーケストレーションを排除します。  
 可能な場合は、全体的なスループットが向上し、ビジネス プロセスの待機時間を短縮するためのオーケストレーションの使用を最小限に抑えます。 長時間実行する必要が実行されていないトランザクションと、要求ごとに複数のシステムを起動する必要はありませんが、検討してくださいオーケストレーションを排除し、ビジネス ロジックをへのラウンドト リップの合計量を削減するには、受信と送信ポートに移動しますBizTalkMsgBoxDb とデータベースへのアクセスのための待機時間が減少します。 この場合は、カスタム パイプラインを実装し、オーケストレーションから呼び出された以前ヘルパー クラスを再利用します。 散布図や収集や、コンボイのデザイン パターンを実装するには、厳密に必要な場合にのみ、オーケストレーションを使用します。 オーケストレーションのデザイン パターンの詳細については、トピックを参照してください。[オーケストレーションのデザイン パターンを実装する](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) 、BizTalk Server のドキュメントにします。  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a>低待機時間シナリオに対応するために使用してインラインはオーケストレーションから送信します  
 可能であれば、オーケストレーションの使用を最小限に抑えるし、全体的なスループットを向上させる、ビジネス プロセスの待機時間を短縮してメッセージングのみのパターンを優先します。 実行時間の長いトランザクションの必要性がなく、ビジネス ロジックをいくつかのシステムを呼び出す必要はない場合、は、受信し、送信ポートにビジネス ロジックを移動して、オーケストレーションの使用を排除することを検討しています。 カスタム パイプラインでこのアプローチを実装することができ、オーケストレーションから呼び出された以前ヘルパー クラスを再利用します。 低待機時間シナリオでパフォーマンスの向上を実現するために、次の方法のいずれかを採用します。  
  
-   不要なオーケストレーションを排除し、BizTalk メッセージ ボックス データベースへのラウンド トリップの合計量を削減するメッセージングのみのパターンを採用します。 このアプローチはインライン送信のバイパス、BizTalk メッセージング エンジンと関連付けられているため、低待機時間に対応のオーバーヘッド。 BizTalk Server 2006 以降のバージョンと、オーケストレーション インライン送信機能が提供されます。  
  
-   内側のオーケストレーションは、物理ポートにバインドされた論理ポートを排除し、代わりに使用して行を送信します。 たとえば、インライン送信は、ダウン ストリーム Web サービスまたは SQL Server データベースへのアクセスに ADO.NET コンポーネントを呼び出す、WCF プロキシ クラスのインスタンスを作成する管理される可能性があります。 オーケストレーションが内部的には、WCF の使用して、業務のコンポーネントをインスタンス化するときに実行する、インライン送信では、次の図では、ダウン ストリーム Web サービスの直接呼び出しオブジェクトをプロキシします。  
  
     ![BizTalk オーケストレーション インライン送信の説明図](../technical-guides/media/inlinesend.gif "InlineSend")  
  
> [!NOTE]
>  オーケストレーション インライン送信を使用すると、待機時間が大幅に少なくは、この方法に制限があります。 インラインの送信は、BizTalk メッセージング エンジンをバイパスするため、次に、メッセージング エンジンによって提供される機能は使用できません。  
> 
> - トランザクション パイプライン  
>   -   回復可能パイプライン。  
>   -   BAM インターセプター API を呼び出すパイプライン  
>   -   BizTalk Server アダプターのサポート  
>   -   バッチ処理  
>   -   [再試行の回数]  
>   -   関連付けセットの初期化  
>   -   宣言型の構成  
>   -   セカンダリ トランスポート  
>   -   Tracking  
>   -   BAM の宣言型の使用  
  
 オーケストレーション内から実行することはできませんのパイプラインの種類の詳細については、トピックの「制限事項」セクションを参照してください[パイプラインの実行に式を使用する方法](http://go.microsoft.com/fwlink/?LinkId=158008)(http://go.microsoft.com/fwlink/?LinkId=158008) BizTalk server。2010 のドキュメント。  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a>可能であれば、永続化ポイントの数を減らすことで、オーケストレーションの待機時間を最適化します。  
 のみ、オーケストレーションの範囲としてマークする必要がある"実行時間の長いトランザクション"補正またはスコープのタイムアウトを使用する場合。 実行時間の長いトランザクションのスコープは補正またはスコープのタイムアウトを使用する必要がないときに、避ける必要がありますので、スコープの最後に、余分な永続化ポイントをによりします。 アトミックのスコープは、スコープの最後の永続化ポイントもアトミックのスコープで永続化ポイントが発生しないことが保証されます。 (複数の実行を送信するときなど)、バッチの永続化ポイントする方が得策ない永続化、スコープ内でのこの副作用を使用こともありますできます。 一般に、ただし、できるだけアトミックのスコープ可能な場合。 オーケストレーション エンジンは、永続的ストレージに全体の状態を保存さまざまなポイントで実行中のオーケストレーション インスタンス、インスタンスは後でメモリ内で復元および完了するために実行できるようにします。   
**オーケストレーションの永続化ポイントの数は、オーケストレーションを通過するメッセージの待機時間に影響を与える主な要因の 1 つ**します。 エンジンは、永続化ポイントをヒットするたびに実行中のオーケストレーションの内部状態をシリアル化され、メッセージ ボックス データベースに保存し、この操作が待機時間のコストが発生します。 内部の状態のシリアル化には、すべてのメッセージおよびインスタンス化され、オーケストレーションで公開されていない変数が含まれています。 大きいほど、メッセージおよび変数とそれらの数が大きいほど、長くかかりますオーケストレーションの内部状態を保持します。 永続化ポイントの数が多すぎるは、パフォーマンスが著しく低下につながります。 このためはトランザクション スコープの数を減らすことで、オーケストレーションからの不要な永続化ポイントを排除することをお勧めし、送信図形。 これにより、全体的なスケーラビリティを向上させると、オーケストレーションの遅延時間の短縮により、オーケストレーションの退避と復元、MessageBox に競合が少なくできます。   
別の推奨事項では、常にオーケストレーションの内部状態をできるだけ小さくしてください。 この手法では、シリアル化、永続化および永続化ポイントが発生した場合、オーケストレーションの内部状態の復元は、XLANG エンジンで費やされた時間を大幅に短縮できます。 これを実現する方法の 1 つは、できるだけ変数と、遅延メッセージを作成し、できるだけ早くリリースとして可能ですたとえば、オーケストレーション内で非トランザクションのスコープを紹介し、変数とそれらを最上位レベルで宣言する代わりにこれらの内部スコープ内のメッセージを宣言します。 オーケストレーションの永続化ポイントを最小限に抑えることの詳細については、BizTalk Server 2010 のドキュメントでは、次のトピックを参照してください。  
  
-   [永続性とオーケストレーション エンジン](http://go.microsoft.com/fwlink/?LinkID=155292)(http://go.microsoft.com/fwlink/?LinkID=155292)します。  
  
-   [オーケストレーションの退避と復元](http://go.microsoft.com/fwlink/?LinkID=155284)(http://go.microsoft.com/fwlink/?LinkID=155292)します。  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a>使用するためのガイドラインは、オーケストレーションからメッセージのタグをアクセスまたは属性のプロパティを昇格  
 プロパティを昇格する場合は、メッセージのルーティング、フィルター、およびメッセージの関連付けに使用されるプロパティのみを昇格します。 各プロパティの昇格では、逆アセンブラー コンポーネント (XML、フラットなカスタム) をドキュメントの種類を認識し、ドキュメントの種類を定義する XSD に含まれる相対注釈からの XPath 式を使用して、メッセージからデータを取得する必要があります。 さらに、各プロパティの昇格では、メッセージ エージェントは、メッセージ ボックス データベースにメッセージを公開する場合、bts_InsertProperty ストアド プロシージャの別個の呼び出しが発生します。 オーケストレーションは、特定の要素または属性に含まれる XML ドキュメントにアクセスする必要がある場合、は、次の手法の 1 つを使用します。  
  
- 書き込みや昇格させたプロパティの数を削減し、厳密には必要ないものを排除します。  
  
- 不要な識別フィールドを削除します。 識別フィールドには、コンテキスト プロパティが書き込まれ、その名前がデータを取得するために使用される XPath 式と同じように簡単に重要な領域を占めることができます。 識別プロパティは、ドキュメント型を定義する XSD の注釈として定義されます。 逆アセンブラー コンポーネントでは、昇格させたプロパティを採用して同じアプローチを使用し、受信ドキュメント内で検索する識別フィールドを定義する XPath 式を使用します。 次に、逆アセンブラー コンポーネントは、コンテキストのプロパティを書き込みます場所。  
  
  - **名前**: 注釈で定義された XPath 式。  
  
  - **値**: 受信ドキュメント内で XPath 式で識別される要素の値。  
  
    XPath 式は、対象の要素がドキュメント スキーマで非常に深い場合に特に非常に長いです。 これをより識別フィールドより大きなコンテキストのサイズ。 これにより、全体的なパフォーマンスがさらに悪影響を及ぼします。  
  
- オーケストレーション ランタイムによって提供される XPath 組み込み関数を使用します。  
  
- メッセージが非常に小さい場合 (数キロバイト) と XML 形式の .NET クラスのインスタンスにメッセージを逆シリアル化してパブリック フィールドとプロパティを操作します。 メッセージには、複雑な詰める (カスタム コード、ビジネス ルール エンジン ポリシーなど) が必要がある場合ははるかに高速 XPath 式を使用して、.NET クラスのインスタンスによって公開されるプロパティを使用してデータにアクセスします。 オーケストレーションによって呼び出されるビジネス ロジックが完了したら、エンティティ オブジェクトは BizTalk メッセージにシリアル化できます。 .NET クラスを作成するには、次のツールのいずれかを使用して XML スキーマから: XSD ツール (.NET Framework 2.0) または SVCUTIL (.NET Framework 3.0)。  
  
- オーケストレーションからヘルパー コンポーネントを有効にします。 この手法では、識別フィールドを使用する利点があります。 XPath のため、XPath 式を変更するときは変更する必要はありません (構成ファイル、SSO 構成ストア、カスタム Db、およびなど) を構成から式が格納および再デプロイすると、スキーマが昇格させたプロパティや d を行う必要があります、オーケストレーションが実際には、読み取ることができます。istinguished フィールドです。 次のコード サンプルでは、ヘルパー コンポーネントの例を示します。 コンポーネントは、BizTalk ランタイムによって提供される XPathReader クラスを使用します。 これにより、XPath 式が見つかるまで、ドキュメント ストリームを読み取るコード。  
  
```  
#region Copyright  
//===  
//Microsoft Windows Server AppFabric Customer Advisory Team (CAT)   
//  
// This sample is supplemental to the technical guidance published on the community  
// blog.  
//   
// Author: Paolo Salvatori.  
//===  
// Copyright © 2010 Microsoft Corporation. All rights reserved.  
//   
// THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER   
// EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF   
// MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. YOU BEAR THE RISK OF USING IT.  
//===  
#endregion  
#region Using Directives  
using System;  
using System.Collections.Generic;  
using System.IO;  
using System.Xml;  
using System.Linq;  
using System.Text;  
using System.Globalization;  
using Microsoft.XLANGs.BaseTypes;   
using Microsoft.BizTalk.Streaming;  
using Microsoft.BizTalk.XPath;  
#endregion  
namespace Microsoft.AppFabric.CAT.Samples.DuplexMEP.Helpers  
{  
public class XPathHelper  
{  
#region Private Constants   
private const string MessageCannotBeNull = "[XPathReader] The message cannot be null.";  
#endregion  
#region Public Static Methods  
public static string GetValue(XLANGMessage message, int partIndex, string xpath)  
{  
try  
{  
if (message == null)  
{  
throw new ApplicationException(MessageCannotBeNull);  
}  
using (Stream stream = message[partIndex].RetrieveAs(typeof(Stream)) as Stream)  
{  
XmlTextReader xmlTextReader = new XmlTextReader(stream);  
XPathCollection xPathCollection = new XPathCollection();  
XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
xPathCollection.Add(xpath);  
while (xPathReader.Read())  
{  
if (xPathReader.HasAttributes)  
{  
for (int i = 0; i < xPathReader.AttributeCount; i++)  
{  
xPathReader.MoveToAttribute(i);  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.GetAttribute(i);  
}  
}  
}  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.ReadString();  
}  
}  
}  
}  
finally  
{  
message.Dispose();  
}  
return string.Empty;  
}  
#endregion  
}  
}  
```  
  
## <a name="minimize-orchestration-complexity-to-improve-performance"></a>パフォーマンスを向上させるためにオーケストレーションの複雑さを最小限に抑える  
 オーケストレーションの複雑さは、パフォーマンスに大きな影響を及ぼします。 オーケストレーションの複雑さの増大に合わせて、全体的なパフォーマンスが低下します。 オーケストレーションは、ほぼ無限さまざまなシナリオで使用でき、各シナリオは、複雑さの異なるオーケストレーションを伴う場合があります。 モジュール式の手法を優先して可能な場合は、複雑なオーケストレーションを回避します。 つまり、ビジネス ロジックを複数に分割再利用可能なオーケストレーションします。  
  
 複雑なオーケストレーションを実装する必要がある場合は、メッセージや変数をルート レベルではなく、可能な限り、内側のスコープに定義します。 この手法は、変数およびメッセージが破棄され、フローが変数およびメッセージが定義された範囲を離れるために、オーケストレーションごとのメモリのフット プリントがより小さいを保持します。 この方法は、オーケストレーションが永続化ポイントでメッセージ ボックス データベースに保存されるときに特に有用です。  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a>パフォーマンスを向上させるために、オーケストレーションの開始図形とオーケストレーションの呼び出し図形を使用します。  
 回避、**オーケストレーションの開始**図形し、を使用して、**オーケストレーションの呼び出し**図形を入れ子になったオーケストレーションを実行します。 実際には、**オーケストレーションの呼び出し**を別のプロジェクトで参照されているオーケストレーションを同期的に呼び出す図形を使用することができます。 このアプローチは、BizTalk プロジェクト間での一般的なオーケストレーション ワークフロー パターンの再利用できます。 同期的に入れ子になった別のオーケストレーションを呼び出すと、**オーケストレーションの呼び出し**続行する前に完了する入れ子になったオーケストレーションの図形、外側のオーケストレーションを待機します。 入れ子になったオーケストレーションは、呼び出し元のオーケストレーションを実行している同じスレッドで実行されます。  
  
 **オーケストレーションの開始**図形と似ています、**オーケストレーションの呼び出し**図形、ネストされているオーケストレーションが非同期的に呼び出されるこの場合: 呼び出し元のコントロールのフローオーケストレーションは、呼び出されたオーケストレーションの処理を完了するを待たず、次に処理されます。 呼び出し元から呼び出されたオーケストレーションでは、この分離を実装するために、**オーケストレーションの開始**BizTalk メッセージ ボックスへのメッセージのパブリケーションを介して実装されます。 このメッセージは、入れ子になったオーケストレーションを実行するインプロセス BizTalk ホスト インスタンスによって使用されます。 可能であればを使用して、**オーケストレーションの呼び出し**、呼び出し元のオーケストレーションが処理を続行するには、入れ子になったオーケストレーションからの結果を待機する必要がある場合に特にです。  詳細については、オーケストレーションの呼び出し図形を使用して、BizTalk Server 2010 のドキュメントでは、次のトピックを参照してください。  
  
-   [オーケストレーションでの直接バインド ポートの操作](http://go.microsoft.com/fwlink/?LinkId=139902)(http://go.microsoft.com/fwlink/?LinkId=139902)します。  
  
-   [オーケストレーションを入れ子](http://go.microsoft.com/fwlink/?LinkId=139903)(http://go.microsoft.com/fwlink/?LinkId=139903)します。  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a>XmlDocument を使用したオーケストレーションのパフォーマンスを向上させるために XmlReader を使用すると、XLANGMessage を XmlReader を使用します。  
 オーケストレーションから呼び出される .NET メソッドのオーケストレーションのパフォーマンスを向上させるのには、XLANGMessage、XmlDocument ではないと XmlReader を使用します。 次のコード例は、この機能を示しています。  
  
```csharp  
// As a general rule, use XmlReader with XLANGMessage, not XmlDocument.   
// This is illustrated in the parameter passed into the following code.   
// The XLANG/s compiler doesn't allow a return value of XmlReader   
// so documents must be initially constructed as XmlDocument()  
public static XmlDocument FromMsg(XLANGMessage old)  
{  
    //get at the data  
    XmlDocument ret = new XmlDocument();  
  
    try{  
        XmlReader reader = (XmlReader)old[0].RetrieveAs(typeof(XmlReader));  
        //construct new message from old  
        //read property  
        object msgid = old.GetPropertyValue(typeof(BTS.MessageID));  
    }  
    finally {  
        // Call Dispose on the XLANGMessage object   
        // because the message doesn't belong to the   
        // .NET runtime - it belongs to the Messagebox database   
        old.Dispose();  
    }  
    return ret;  
}  
```  
  
 別の方法は、スキーマに基づく .NET クラスを作成することです。 これにかかる時間にドキュメントの読み込みよりもメモリが少ない、 **XmlDocument** .NET 開発者向けのスキーマ要素に簡単にアクセスを提供するだけでなく、オブジェクト。 BizTalk スキーマに基づくクラスを生成するには、Visual Studio に付属する xsd.exe ツールを使用できます。 たとえば、実行している**xsd.exe \<schema.xsd\> /classes** ItemB、ItemC、ItemA という名前のフィールドを含む単純なスキーマに対して、次のクラスが生成されます。  
  
```csharp  
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:2.0.50727.1433  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
using System.Xml.Serialization;  
  
//   
// This source code was auto-generated by xsd, Version=2.0.50727.42.  
//  
  
/// <remarks/>  
[System.CodeDom.Compiler.GeneratedCodeAttribute("xsd", "2.0.50727.42")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://Schemas.MySchema")]  
[System.Xml.Serialization.XmlRootAttribute(Namespace="http://Schemas.MySchema", IsNullable=false)]  
public partial class MySchemaRoot {  
  
    private string itemAField;  
  
    private string itemBField;  
  
    private string itemCField;  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemA {  
        get {  
            return this.itemAField;  
        }  
        set {  
            this.itemAField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemB {  
        get {  
            return this.itemBField;  
        }  
        set {  
            this.itemBField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemC {  
        get {  
            return this.itemCField;  
        }  
        set {  
            this.itemCField = value;  
        }  
    }  
}  
```  
  
 メッセージの要素にアクセスするには、.NET アセンブリでこのクラスを参照しでき、返されたオブジェクトは、メッセージに直接割り当てることができます。 上記で生成されたクラスの使用例を次に示します。  
  
```csharp  
public static Root SetValues(Microsoft.XLANGs.BaseTypes.XLANGMessage msg)  
{  
   try  
   {  
   MySchemaRoot rootObj=(MySchemaRoot)msg[0].RetrieveAs(typeof(MySchemaRoot);  
   rootObj.ItemA="value a";  
   rootObj.ItemB="value b";  
   rootObj.ItemC="value c";  
   }  
    finally {  
        msg.Dispose();  
            }  
  
   return rootObj;  
}  
```  
  
 この手法を使用すると、メッセージを処理するときに、オブジェクト指向のアプローチを使用できます。 この方法は、比較的小さなメッセージで主に使用する必要があります。 これは、ため、この手法がときにメッセージを読み込むよりも大幅に少ないメモリを使用する場合でも、 **XmlDocument**オブジェクト、メッセージ全体をメモリに読み込まれたままです。 サイズの大きいメッセージを処理する際に使用して、 **XmlReader**メッセージを読み取るクラスと**XmlWriter**クラスのメッセージを書き込みます。 使用する場合**XmlReader**と**XmlWriter**に、メッセージが含まれている、 **VirtualStream**オブジェクト。 メッセージのサイズが指定された値を超えた場合**サイズの大きいメッセージのしきい値 (バイト単位)** BizTalk グループのプロパティの構成 ページで、公開では、メッセージは、ファイル システムに書き込まれます。 これにより、全体のパフォーマンスが低下が、メモリ不足の例外を回避できます。  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a>物理ポートにバインドされた論理ポートの使用を最小限に抑えることによるパフォーマンスを向上します。  
 次のアダプターを使用する物理ポートにバインドされた論理ポートの使用を最小限に抑えることでパフォーマンスを向上できます。  
  
- SQL Server、Oracle  
  
- WSE、HTTP の場合、WCF  
  
- MSMQ、MQSeries  
  
  BizTalk Server 2010 での送信し、受信パイプラインは、Microsoft.XLANGs.Pipeline.dll に含まれている XLANGPipelineManager クラスを使用してオーケストレーションから直接呼び出すことができます。 したがって、パイプラインの処理に移動できますポートからオーケストレーションです。オーケストレーションの論理ポートは、式図形を持ち、特定の .NET クラスのインスタンス (たとえば、ADO.NET を使用してデータ アクセス コンポーネント) を呼び出す代わりに使用できます。 この手法を採用する前に、アダプターと物理ポートを使用しない場合、バッチ処理、再試行、宣言型の構成、およびセカンダリ トランスポートなど、その機能を活用する機能を紛失したこと注意する必要があります。  
  
## <a name="orchestration-design-patterns"></a>オーケストレーションのデザイン パターン  
 オーケストレーション デザイナーでは、さまざまなエンタープライズ統合パターンを実装できます。 いくつかの一般的なパターンには、アグリゲーター、例外処理し補正、メッセージ ブローカー、散布図とギャザー、シーケンシャル モードとパラレルなコンボイが含まれます。 これらのパターンは、BizTalk Server での複雑なエンタープライズ アプリケーション統合 (EAI)、サービス指向アーキテクチャ (SOA)、およびビジネス プロセス管理 (BPM) ソリューションの開発を活用できます。 オーケストレーションのデザイン パターンの詳細については、トピックを参照してください[オーケストレーションのデザイン パターンを実装する](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) BizTalk Server のドキュメントと[パターンとベスト プラクティス。エンタープライズ統合](http://go.microsoft.com/fwlink/?LinkId=140043)(http://go.microsoft.com/fwlink/?LinkId=140043)します。  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a>パフォーマンスを最大化するためのオーケストレーションでの .NET クラスの適切な使用を行う  
 一般に、オーケストレーション内で使用される .NET クラスは、2 つのカテゴリに分類できます。  
  
-   **ヘルパーとサービス -** これらのクラスは、トレース、エラー処理、キャッシュ、およびシリアル化/逆シリアル化などのオーケストレーションに共通のサービスを提供します。 これらのクラスのほとんどは、内部状態がないと複数のパブリック静的メソッドと静的クラスとして実装できます。 このアプローチは、ホスト プロセスの作業領域を減らすし、メモリを節約する同時に実行されている別のオーケストレーションで、同じクラスの複数のオブジェクトの作成を回避できます。 ステートレスであるクラスでは、シリアル化して、オーケストレーションが退避済みの場合は、BizTalk メッセージ ボックスに永続化される必要がある内部状態の全体的なサイズを削減できます。  
  
-   **エンティティおよびビジネス オブジェクト -** 注文、注文番号の品目、および顧客などのエンティティを管理するこれらのクラスを使用することができます。 1 つのオーケストレーションは、内部的に作成し、同じ種類の複数のインスタンスを管理できます。 これらのクラスは通常ステートフルであり、パブリック フィールドや、オブジェクトの内部状態を変更するメソッドとプロパティを公開します。 使用して .NET オブジェクトに、XLANGMessage 部分を逆シリアル化して、これらのクラスのインスタンスを動的に作成することができます、 **XmlSerializer**または**DataContractSerializer**クラスか、を使用して**XLANGPart.RetrieveAs**メソッド。 ステートフルなクラスのインスタンスができるだけ遅く作成され、不要にするとすぐに解放する方法で非トランザクションのスコープを使用するオーケストレーションを構成する必要があります。 このアプローチでは、ホスト プロセスの作業領域が抑制され、シリアル化し、オーケストレーションが退避済みの場合は、メッセージ ボックス データベースに永続化の内部状態の全体的なサイズを最小限に抑えられます。 詳細については、BizTalk server オーケストレーションを使用して、記事を参照してください。 [BizTalk Server オーケストレーションのよく寄せられる質問](http://go.microsoft.com/fwlink/?LinkID=116886)(http://go.microsoft.com/fwlink/?LinkID=116886)します。  
  
    > [!NOTE]  
    >  この記事では、BizTalk Server 2004 および BizTalk Server 2006 用に記述されたが、説明する概念も BizTalk Server 2010 のオーケストレーションに適用されます。  
  
## <a name="orchestration-exception-handler-blocks"></a>オーケストレーションの例外ハンドラー ブロック  
 オーケストレーションの例外ハンドラー ブロックを使用する場合は、1 つまたは複数のスコープ (可能な限り非トランザクション スコープ) にすべてのオーケストレーション図形を含めるし、少なくとも次の例外ハンドラー ブロックを作成します。  
  
- System.Exception の一般的なエラーを処理するための例外ハンドラー ブロックします。  
  
- 例外ハンドラー ブロックにキャッチして COM 例外など、管理されていないエラーを処理するために、一般的な例外を処理するためです。  
  
  詳細については、オーケストレーションの例外処理ブロックを使用して、次の記事を参照してください。  
  
- [BizTalk Server 例外処理を使用して](http://msdn.microsoft.com/library/aa561229.aspx)(http://msdn.microsoft.com/library/aa561229.aspx)します。  
  
- [Charles Young のブログ、BizTalk Server 2006: 補正モデル](http://go.microsoft.com/fwlink/?LinkId=158017)(http://go.microsoft.com/fwlink/?LinkId=158017)します。  
  
  > [!NOTE]
  >  このブログで書き込まれたときに[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]を考慮して、ブログで説明する原則にも適用 BizTalk Server です。  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a>オーケストレーションでマップを使用する際の考慮事項  
 オーケストレーションでマップを使用する場合は、次の考慮事項が適用されます。  
  
-   抽出または使用するプロパティを設定するマップを使用している場合、オーケストレーションでビジネス ロジックは識別フィールドを使用して、または昇格させたプロパティです。 この実習を抽出したり、ドキュメント マップで値の設定が読み込まれるときにメモリにただし識別フィールドまたは昇格させたプロパティを使用して、オーケストレーション エンジンがメッセージ コンテキストにアクセスして、読み込まれませんので、従う必要があります、ドキュメントをメモリにします。  
  
-   マップを使用して、複数のフィールドを 1 つのフィールドで集計している場合、識別フィールドまたはオーケストレーションの変数が設定されている昇格したプロパティを使用して、結果セットを累積してください。  
  
## <a name="see-also"></a>参照  
 [パフォーマンスの最適化](../technical-guides/optimizing-performance.md)