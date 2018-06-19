---
title: オーケストレーションのパフォーマンスの最適化 |Microsoft ドキュメント
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
ms.openlocfilehash: b4f8a3b0bcc58fbed428152bb9f55c34d867258a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010395"
---
# <a name="optimizing-orchestration-performance"></a>オーケストレーションのパフォーマンスを最適化します。
このトピックでは、BizTalk Server ソリューションのオーケストレーションを使用するためのベスト プラクティスについて説明します。 これには、推奨事項が含まれます。  
  
-   オーケストレーションを使用する BizTalk Server ソリューションの待ち時間の短縮  
  
    -   メッセージングのみのパターンのオーケストレーションを排除すること  
  
    -   オーケストレーションから送信インラインを利用します。  
  
    -   オーケストレーションの永続化ポイントを最小限に抑える  
  
-   オーケストレーションを入れ子  
  
-   オーケストレーションのデザイン パターン  
  
-   オーケストレーションの例外処理ブロック  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a>低待機時間シナリオでオーケストレーションを最適化するための推奨事項  
 オーケストレーションを使用する BizTalk Server ソリューションの待機時間を短縮する、次の手法を使用できます。  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a>メッセージングのみのパターンのオーケストレーションを排除します。  
 可能な場合は、全体的なスループットが向上し、ビジネス プロセスの待機時間を短縮するためのオーケストレーションの使用を最小限に抑えます。 長いを実行する必要が実行されていないトランザクションと、要求ごとに複数のシステムを起動する必要はありませんが場合を検討してオーケストレーションを排除し、ビジネス ロジックをへのラウンドト リップの合計量を削減するには、受信と送信ポートに移動しますBizTalkMsgBoxDb およびデータベースへのアクセス待機時間が低下します。 この例では、カスタム パイプラインを実装し、オーケストレーションから起動していた以前のヘルパー クラスを再利用します。 散布図や収集や、コンボイのデザイン パターンを実装するには、厳密に必要な場合にのみ、オーケストレーションを使用します。 オーケストレーションのデザイン パターンの詳細については、トピックを参照してください。[オーケストレーションのデザイン パターンを実装する](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042)、BizTalk Server のドキュメントにします。  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a>低待機時間シナリオに合わせてインラインを使用するがオーケストレーションから送信します。  
 可能な限り、オーケストレーションの使用を最小限に抑えるし、全体的なスループットを上げるし、ビジネス プロセスの待機時間を短縮するメッセージングのみのパターンを優先します。 実行時間の長いトランザクションの必要はありませんし、ビジネス ロジックをいくつかのシステムを呼び出す必要はない場合、は、受信し、送信ポートにビジネス ロジックを移動し、オーケストレーションの使用を排除することを検討しています。 カスタム パイプラインでこのアプローチを実装することができ、オーケストレーションから起動していた以前ヘルパー クラスを再利用します。 低待機時間シナリオでパフォーマンスの向上を実現するために、次のいずれかを採用します。  
  
-   不要なオーケストレーションを排除し、BizTalk メッセージ ボックス データベースへのラウンド トリップの合計量を削減するメッセージングのみのパターンを採用します。 このアプローチがインラインの送信を回避する、BizTalk メッセージング エンジンと、関連付けられているために、低待機時間を対応のオーバーヘッドです。 BizTalk Server 2006 以降のバージョンと、オーケストレーション インライン送信の機能は提供されます。  
  
-   内側オーケストレーションが物理ポートにバインドされた論理ポートを除去し、代わりに使用する行を送信します。 たとえば、インライン送信もダウン ストリーム Web サービスまたは SQL Server データベースへのアクセスに ADO.NET コンポーネントを呼び出す、WCF プロキシ クラスのインスタンスを作成できます。 次の図では、インライン送信の実行、オーケストレーションが内部的には、WCF の使用して、業務のコンポーネントをインスタンス化するとき、ダウン ストリーム Web サービスを直接起動するプロキシ オブジェクト。  
  
     ![BizTalk オーケストレーション インライン送信の説明図](../technical-guides/media/inlinesend.gif "InlineSend")  
  
> [!NOTE]  
>  オーケストレーション インライン送信を使用すると、待機時間が大幅に少なくがこの方法に制限します。 インライン送信は、BizTalk メッセージング エンジンをバイパスするため、メッセージング エンジンによって提供される次の機能は使用できません。  
>   
>  -   トランザクション パイプライン  
> -   回復可能パイプライン。  
> -   BAM インターセプター API を呼び出すパイプライン  
> -   BizTalk Server アダプターのサポート  
> -   バッチ処理  
> -   [再試行の回数]  
> -   関連付けセットの初期化  
> -   宣言型の構成  
> -   セカンダリ トランスポート  
> -   Tracking  
> -   BAM の宣言型の使用  
  
 オーケストレーション内から実行することはできませんのパイプラインの種類の詳細については、トピックの「制限」セクションを参照してください。[パイプライン実行表現を使用する方法](http://go.microsoft.com/fwlink/?LinkId=158008)(http://go.microsoft.com/fwlink/?LinkId = 158008)、BizTalk Server 2010 ドキュメント。  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a>可能であれば、永続化ポイントの数を減らすことによってオーケストレーションの待機時間を最適化します。  
 のみオーケストレーション範囲をマークを付ける必要がある"実行時間の長いトランザクション"補正またはスコープのタイムアウトを使用する場合。 実行時間の長いトランザクションのスコープは、補正またはスコープのタイムアウトを使用する必要があるに回避する必要がありますので、スコープの最後に、余分な永続化ポイントをさせます。 アトミックのスコープは、スコープの最後の永続化ポイントもアトミックのスコープ内で永続化ポイントが発生しないことを保証します。 (複数の実行を送信するときなど)、この副作用として、スコープ内で持続性のないは場合もあります有利バッチ永続化ポイントに使用できます。 一般に、ただし、ことをお勧め可能な場合にアトミックのスコープを回避します。 オーケストレーション エンジンは、永続的ストレージに全体の状態を保存さまざまな時点で、実行中のオーケストレーション インスタンス、インスタンスは後でメモリに復元および完了するために実行できるようにします。   
**オーケストレーションの永続化ポイントの数はオーケストレーション経由でやり取りされるメッセージの待機時間に影響を与える主な要因の 1 つ**です。 エンジンが、永続化ポイントをヒットするたびに実行中のオーケストレーションの内部状態をシリアル化され、メッセージ ボックス データベースに保存し、この操作の待機時間に課金します。 内部状態のシリアル化には、すべてのメッセージおよびインスタンス化され、オーケストレーションでリリースされていない変数が含まれています。 大きいほど、メッセージおよび変数とこれらの数が多くの場合は、時間が長くなるにかかるオーケストレーションの内部状態を維持します。 永続化ポイントの数が多すぎるは、パフォーマンスが大幅に低下する可能性があります。 このため、トランザクション スコープの数を減らすことによってオーケストレーションから不要な永続化ポイントを排除することをお勧めし、送信図形。 これにより、全体的なスケーラビリティを向上させると、オーケストレーションの待機時間を減らすことにより、オーケストレーションの退避と復元、MessageBox に競合を削減できます。   
別の推奨設定では、常に、オーケストレーションの内部状態をできるだけ小さくしてください。 この手法では、XLANG エンジンのシリアル化、永続化および永続化ポイントが発生した場合、オーケストレーションの内部状態を復元するのにかかった時間を大幅に削減できます。 これを実現する方法の 1 つをできるだけ変数および遅延にメッセージを作成し、できるだけ早くリリースできるだけです。たとえば、オーケストレーション内の非トランザクションのスコープを紹介し、変数とその最上位のレベルで宣言する代わりにこれらの内部スコープ内でメッセージを宣言します。 詳細については、オーケストレーションの永続化ポイントを最小限に抑え、BizTalk Server 2010 のドキュメントの次のトピックを参照してください。  
  
-   [永続化し、オーケストレーション エンジン](http://go.microsoft.com/fwlink/?LinkID=155292)(http://go.microsoft.com/fwlink/?LinkID=155292)。  
  
-   [オーケストレーションの退避と復元](http://go.microsoft.com/fwlink/?LinkID=155284)(http://go.microsoft.com/fwlink/?LinkID=155292)。  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a>昇格させたプロパティは、アクセス メッセージ タグまたは属性をオーケストレーションからの使用に関するガイドライン  
 プロパティを昇格する場合は、メッセージのルーティング、フィルター、およびメッセージの関連付けに使用されるプロパティだけを昇格します。 各プロパティの昇格では、逆アセンブラー コンポーネント (フラット、カスタムの XML、) をドキュメントの種類を認識し、ドキュメントの種類を定義する XSD に含まれる相対注釈からの XPath 式を使用して、メッセージからデータを取得する必要があります。 さらに、各プロパティの昇格では、メッセージ エージェントは、メッセージ ボックス データベースにメッセージを公開する際に bts_InsertProperty ストアド プロシージャの別個の呼び出しが発生します。 オーケストレーションは、特定の要素または属性に含まれる XML ドキュメントにアクセスする必要がある場合、は、次の手法のいずれかを使用します。  
  
-   書き込まれると昇格させたプロパティの数を削減し、厳密には必要なものを排除します。  
  
-   不要な識別フィールドを削除します。 識別フィールドには、コンテキスト プロパティが書き込まれ、その名前がデータを取得するために使用する XPath 式と同じように、簡単に重要な領域を占有する可能性がします。 識別プロパティは、ドキュメントの種類を定義する XSD の注釈として定義されます。 逆アセンブラー コンポーネントは、昇格させたプロパティを採用して同じアプローチを使用しを受信ドキュメント内で検索する識別フィールドを定義する XPath 式を使用します。 次に、逆アセンブラー コンポーネントは、コンテキストにプロパティを書き込みます場所。  
  
    -   **名前**: 注釈で定義されている XPath 式。  
  
    -   **値**: 受信ドキュメント内で XPath 式で識別される要素の値。  
  
     特に該当の要素がドキュメント スキーマで非常に深い場合は、XPath 式が非常に長いに指定できます。 このためより識別フィールドを大きい方のコンテキストのサイズ。 これにより、全体的なパフォーマンスがさらに悪影響を及ぼします。  
  
-   オーケストレーション ランタイムによって提供される XPath 組み込み関数を使用します。  
  
-   メッセージが非常に小さい場合 (数キロバイト) XML 形式の .NET クラスのインスタンスにメッセージを逆シリアル化してパブリック フィールドとプロパティを操作します。 メッセージには、複雑な完了 (カスタム コード、ビジネス ルール エンジン ポリシーなど) が必要がある場合は、はるかに高速 XPath 式の使用は .NET クラスのインスタンスによって公開されるプロパティを使用してデータにアクセスします。 オーケストレーションによって呼び出されるビジネス ロジックが完了したら、BizTalk メッセージにエンティティ オブジェクトをシリアル化できます。 .NET クラスを作成するには、次のツールのいずれかを使用して XML スキーマから: XSD ツール (.NET Framework 2.0) または SVCUTIL (.NET Framework 3.0)。  
  
-   オーケストレーションからヘルパー コンポーネントを有効にします。 この手法では、識別フィールドを使用する利点があります。 実際には、オーケストレーションは読み取ることが、構成から式を格納 (構成ファイル、SSO 構成ストア、カスタム Db、およびなど) ため、XPath 式を変更する必要があるときは変更する必要はありません XPath と再展開すると、スキーマは、昇格させたプロパティ用および d 行う必要があります。istinguished フィールドです。 次のコード サンプルでは、ヘルパー コンポーネントの例を示します。 コンポーネントは、BizTalk ランタイムによって提供される XPathReader クラスを使用します。 これにより、コードを XPath 式が見つかるまでドキュメント ストリームを読み取る。  
  
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
 オーケストレーションの複雑さは、パフォーマンスに大きな影響を及ぼします。 オーケストレーションの複雑さが多いほど、全体的なパフォーマンスが低下します。 オーケストレーションは、ほぼ無限さまざまなシナリオで使用でき、各シナリオには、複雑さの異なるオーケストレーションが含まれます。 モジュール型のアプローチを優先するために可能な場合は、複雑なオーケストレーションは避けてください。 つまり、ビジネス ロジックを複数に分割再利用可能なオーケストレーションです。  
  
 複雑なオーケストレーションを実装する必要がある場合は、メッセージおよび変数をルート レベルではなく、可能な限り、内側のスコープに定義します。 この手法は、変数およびメッセージが破棄されるのフローが変数およびメッセージが定義されている範囲を離れるために、各オーケストレーション用のメモリの量が削減されを保持します。 この方法は、オーケストレーションが永続化ポイントでメッセージ ボックス データベースに保存されるときに特に有用です。  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a>オーケストレーションの開始図形とオーケストレーションの呼び出し図形を使用してパフォーマンスを向上させる  
 回避、**オーケストレーションの開始**の整形し、を使用して、**オーケストレーションの呼び出し**ネストされているオーケストレーションを実行する図形です。 実際には、**オーケストレーションの呼び出し**図形を同期的に呼び出す別のプロジェクトで参照されているオーケストレーションを使用することができます。 この方法は、BizTalk プロジェクト間での一般的なオーケストレーション ワークフロー パターンの再利用できます。 同期的に入れ子になった別のオーケストレーションを呼び出した場合、**オーケストレーションの呼び出し**図形、外側のオーケストレーションを待って、入れ子になったオーケストレーションを続行する前に完了します。 入れ子になったオーケストレーションは、呼び出し元のオーケストレーションを実行している同じスレッドで実行されます。  
  
 **オーケストレーションの開始**図形がに似ていますが、**オーケストレーションの呼び出し**図形がネストされているオーケストレーションが非同期的に呼び出されましたここで: 呼び出し元に制御フローオーケストレーションは、呼び出されたオーケストレーションがその作業を終了するを待たず、呼び出しを超える処理されます。 呼び出し元と、呼び出されたオーケストレーション間の分離を実装するために、**オーケストレーションの開始**は BizTalk メッセージ ボックスへのメッセージのパブリケーションを使用して実装します。 このメッセージは、ネストされているオーケストレーションを実行するインプロセス BizTalk ホスト インスタンスによって、消費されます。 可能であれば、使用**オーケストレーションの呼び出し**、呼び出し元のオーケストレーションはネストされているオーケストレーションからの結果の処理を続行するために待機する必要がある場合に特にです。  詳細については、オーケストレーションの呼び出し図形を使用して、BizTalk Server 2010 のドキュメントの次のトピックを参照してください。  
  
-   [オーケストレーションでの直接バインド ポートの操作](http://go.microsoft.com/fwlink/?LinkId=139902)(http://go.microsoft.com/fwlink/?LinkId=139902)。  
  
-   [オーケストレーションを入れ子に](http://go.microsoft.com/fwlink/?LinkId=139903)(http://go.microsoft.com/fwlink/?LinkId=139903)。  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a>XLANGMessage の XmlDocument でオーケストレーションのパフォーマンスを向上させるために XmlReader を使用すると XmlReader を使用します。  
 オーケストレーションから呼び出される .NET メソッドをオーケストレーションのパフォーマンスを向上させるのには、XLANGMessage、XmlDocument されませんと XmlReader を使用します。 次のコード例では、この機能について説明します。  
  
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
  
 別の方法は、スキーマに基づく .NET クラスを作成することです。 これにかかる時間にドキュメントの読み込みよりも少ないメモリ、 **XmlDocument**オブジェクトだけでなく .NET 開発者向けのスキーマの要素に簡単にアクセスを提供します。 BizTalk スキーマを基にクラスを生成するには、Visual Studio に付属する xsd.exe ツールを使用できます。 たとえば、実行している**xsd.exe \<schema.xsd\> /classes** ItemB、ItemC、ItemA をという名前のフィールドを含む、単純なスキーマに対して次のクラスが生成されます。  
  
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
  
 メッセージの要素にアクセスするために、.NET アセンブリでこのクラスを参照し、でき、返されたオブジェクトは、メッセージに直接割り当てることができます。 上に生成されたクラスの使用例を次に示します。  
  
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
  
 この手法では、メッセージを処理するときに、オブジェクト指向アプローチを使用することができます。 この方法は、比較的小さいメッセージを主に使用する必要があります。 これは、この手法でにメッセージを読み込むときよりもはるかに小さくメモリがどのように使用されていなくても、 **XmlDocument**オブジェクト、メッセージ全体がメモリに読み込まれたままです。 サイズの大きいメッセージを処理する際に使用して、 **XmlReader**メッセージを読み取るクラスおよび**XmlWriter**メッセージを書き込むためのクラスです。 使用する場合**XmlReader**と**XmlWriter**に、メッセージが含まれている、 **VirtualStream**オブジェクト。 メッセージのサイズが指定された値を超えた場合**サイズの大きいメッセージのしきい値 (バイト単位)** BizTalk グループのプロパティの構成 ページで、公開されるメッセージの書き込み、ファイル システムにします。 これにより、全体のパフォーマンスの低下がメモリ不足の例外を回避できます。  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a>物理ポートにバインドされた論理ポートの使用を最小限に抑え、パフォーマンスが向上します。  
 次のアダプターを使用する物理ポートにバインドされた論理ポートの使用を最小限に抑えることをパフォーマンスを向上させることができます。  
  
-   SQL Server、Oracle  
  
-   WSE、HTTP、WCF  
  
-   MSMQ、MQSeries  
  
 BizTalk Server 2010 で送信および受信パイプラインは、Microsoft.XLANGs.Pipeline.dll に含まれている XLANGPipelineManager クラスを使用してオーケストレーションから直接呼び出すことができます。 したがって、パイプラインの処理に移動できますポートからオーケストレーションです。オーケストレーションの論理ポートは、特定の .NET クラスのインスタンス (たとえば、ADO.NET を使用してデータ アクセス コンポーネント) を呼び出す式図形に置き換えられることができます。 この手法を採用する前にアダプターと物理ポートを使用しない場合、バッチ処理、再試行、宣言型の構成、およびセカンダリ トランスポートなど、その機能を利用できることを紛失したことに注意してください。  
  
## <a name="orchestration-design-patterns"></a>オーケストレーションのデザイン パターン  
 オーケストレーション デザイナーでは、さまざまなエンタープライズ統合パターンの実装をすることができます。 一般的なパターンには、アグリゲーター、例外処理し補正、メッセージ ブローカー、散布図と収集、シーケンシャル モードおよびしてパラレルなコンボイが含まれます。 これらのパターンは、BizTalk Server と複雑なエンタープライズ アプリケーション統合 (EAI)、サービス指向アーキテクチャ (SOA) およびビジネス プロセス管理 (BPM) ソリューションの開発を利用できます。 オーケストレーションのデザイン パターンの詳細については、トピックを参照してください[オーケストレーションのデザイン パターンを実装する](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?。LinkId = 140042)、BizTalk Server のドキュメントと[パターンとエンタープライズ統合のベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=140043)(http://go.microsoft.com/fwlink/?LinkId = 140043)。  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a>パフォーマンスを最大限活用するためのオーケストレーションでの .NET クラスの適切な使用を行う  
 一般に、オーケストレーション内で使用する .NET クラスは、2 つのカテゴリに分類できます。  
  
-   **ヘルパーとサービス -** これらのクラスは、トレース、エラー処理、キャッシュ、およびシリアル化または逆シリアル化などのオーケストレーションに共通のサービスを提供します。 これらのクラスのほとんどは、内部状態がないと複数のパブリック静的メソッドと静的クラスとして実装することができます。 この方法は、ホスト プロセスの作業領域を縮小し、メモリを節約することが同時に実行されている別のオーケストレーションで、同じクラスの複数のオブジェクトの作成を回避できます。 ステートレスであるクラスでは、シリアル化され、オーケストレーションが退避済みの場合、BizTalk メッセージ ボックス データベースに永続化する必要がありますの内部状態の全体的なサイズを削減できます。  
  
-   **エンティティとビジネス オブジェクト -** これらのクラスを使用して、注文、発注品目、顧客などのエンティティを管理することができます。 1 つのオーケストレーションは、内部的に作成し、同じ種類の複数のインスタンスを管理できます。 これらのクラスは通常ステートフルであり、パブリック フィールドや、オブジェクトの内部状態を変更するメソッドとプロパティを公開します。 使用して、.NET オブジェクトに、XLANGMessage 部分を逆シリアル化して、これらのクラスのインスタンスを動的に作成できる、 **XmlSerializer**または**DataContractSerializer**クラスか、を使用して**XLANGPart.RetrieveAs**メソッドです。 ステートフルなクラスのインスタンスが可能な遅延作成され、不要になったとすぐに解放するように非トランザクションのスコープを使用するオーケストレーションを構成する必要があります。 この方法は、ホスト プロセスの作業領域が抑制され、シリアル化され、オーケストレーションが退避済みの場合、メッセージ ボックス データベースに永続化の内部状態の全体的なサイズを最小限に抑えられます。 詳細については、BizTalk server オーケストレーションを使用して、記事を参照してください。 [BizTalk Server オーケストレーションのよく寄せられる質問](http://go.microsoft.com/fwlink/?LinkID=116886)(http://go.microsoft.com/fwlink/?LinkID=116886)。  
  
    > [!NOTE]  
    >  この記事は、BizTalk Server 2004 および BizTalk Server 2006 の書き込みは、中にある概念は、BizTalk Server 2010 のオーケストレーションにも適用されます。  
  
## <a name="orchestration-exception-handler-blocks"></a>オーケストレーションの例外ハンドラー ブロック  
 オーケストレーションの例外ハンドラー ブロックを使用する場合は、1 つまたは複数のスコープ (可能な限りトランザクションではないスコープ) にすべてのオーケストレーション図形を含めるし、少なくとも次の例外ハンドラー ブロックを作成します。  
  
-   System.Exception の一般的なエラーを処理する例外ハンドラー ブロックします。  
  
-   例外ハンドラー ブロックをキャッチして COM 例外など、管理されていないエラーを処理するために、一般的な例外を処理するためです。  
  
 詳細については、オーケストレーションの例外処理ブロックを使用して、次の記事を参照してください。  
  
-   [BizTalk Server 例外処理を使用して](http://msdn.microsoft.com/library/aa561229.aspx)(http://msdn.microsoft.com/library/aa561229.aspx)。  
  
-   [Charles Young ブログ、BizTalk Server 2006: 補正モデル](http://go.microsoft.com/fwlink/?LinkId=158017)(http://go.microsoft.com/fwlink/?LinkId=158017)。  
  
    > [!NOTE]  
    >  このブログで書き込まれたときに[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]念頭ブログで説明した原則にも適用 BizTalk Server です。  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a>オーケストレーションでマップを使用する際の考慮事項  
 オーケストレーションでマップを使用する場合は、次の考慮事項が適用されます。  
  
-   抽出またはで使用するプロパティを設定するマップを使用している場合、オーケストレーションでビジネス ロジックは識別フィールドを使用してまたは昇格させたプロパティです。 抽出またはドキュメント マップで値を設定が読み込まれるときにメモリにただし識別フィールドまたは昇格させたプロパティを使用して、オーケストレーション エンジンは、メッセージ コンテキストにアクセスしてが読み込まれないために、この実習を従う必要があります、メモリにドキュメントです。  
  
-   マップを使用して、複数のフィールドを 1 つのフィールドで集計している場合、識別フィールドまたはオーケストレーションの変数が設定されている昇格したプロパティを使用して、結果セットを累積してください。  
  
## <a name="see-also"></a>参照  
 [パフォーマンスの最適化](../technical-guides/optimizing-performance.md)