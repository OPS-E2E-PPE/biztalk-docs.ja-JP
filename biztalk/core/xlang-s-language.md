---
title: XLANG の言語 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, properties
ms.assetid: 97b62f17-5a8d-4d87-8563-1f6d941f027f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2329d4bc42617d70227481a0d70064d368f3c0e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290914"
---
# <a name="xlang-s-language"></a>XLANG の言語
XLANG/s は、XML、XSD、Web Services Description Language (WSDL) などのインターネット標準を使用するように設計されており、.NET ベースのオブジェクトおよびメッセージの操作に対するサポートが組み込まれています。 XLANG/s は、C# の表現機能を備えたメッセージング言語と見なすことができます。 ただし、XLANG/s と C# の間でコードを移植することはできません。  
  
 XLANG/s では、プロセスと実装を明確に区別することが推奨されています。 たとえば、ビジネス プロセスまたはプロトコルを XLANG/s で指定し、アプリケーションのローカルな側面 (データベース アクセスなど) を他の .NET プログラミング言語 (C# や Visual Basic.NET など) で実装します。  
  
 XLANG/s の割り当て構文および式構文は C# をモデルとしています。したがって、正確な構文については、C# の仕様を参照する必要があります。 XLANG/s では、ビジネス プロセスの定義に使用される高レベルのコンストラクターが多数定義されています。 XLANG/s では、文字列や整数などの低レベルのデータ型がサポートされていますが、メッセージ、ポート、関連付け、サービス リンクなどの高レベルのデータ型も定義されています。 これらのデータ型が厳密に定義する、ビジネス プロセスに関連付けられているセマンティクスが使用され、プロセスによって補完されます制御ステートメントなど**中**または**スコープ**です。  
  
 Xlang/s ステートメントは一般に、2 つのカテゴリのいずれかに分類: 単純なステートメントなど、独自に作用する**受信**または**送信**、および複雑なステートメントに含まれているいずれかの単純なステートメントをグループ化またはその他の複雑なステートメントなど**スコープ**、**並列**、および**リッスン**です。 XLANG/s に組み込まれているセマンティクスは、Microsoft、IBM、および BEA がビジネス プロセスのセマンティクスを定義するために公開した Business Process Execution Language for Web Services (BPEL4WS) 仕様に定義されているセマンティクスを反映したものです。  
  
 XLANG/s の主なコンストラクターは、BizTalk オーケストレーション デザイナーでオーケストレーション ダイアグラムを描画することによって生成されます。したがって、これらのコンストラクターについて理解する必要は必ずしもありません。 オーケストレーション デザイナーは、ビジネス プロセスを視覚的にデザインするための機能豊富なグラフィカル ツールです。 オーケストレーション デザイナーは、.odx という拡張子を持つ XLANG/s ファイルを生成します。このファイルのヘッダーには追加の視覚的情報が格納され、本文にはカスタム属性情報が格納されます。  
  
> [!NOTE]
>  XLANG/s 言語は独自に開発されたもので、仕様は一部非公開となっています。 このセクションでは、この言語について、オーケストレーションを作成する際に注意するべき項目を説明します。 .odx ファイルを直接変更することはサポートされていません。  
  
## <a name="xlangs-programs"></a>XLANG/s プログラム  
 最も単純な XLANG/s プログラムでは、メッセージの種類を定義することにより、操作を開始するためのデータをオーケストレーションに提供する必要があります。 オーケストレーションは、ポート経由でメッセージを受信してから終了します。 コード例は次のとおりです。  
  
```  
module HelloWorldApp  
{  
     private porttype ptPOReceive  
     {  
      oneway opPOReceive  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private porttype ptPOSend  
     {  
      oneway opPOSend  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private service  HelloWorld  
     {  
      port implements HelloWorldApp.ptPOReceive poPOReceive;  
      port uses HelloWorldApp.ptPOSend poPOSend;  
      message HelloWorldApp.PurchaseOrder msgPO;  
      body ()  
      {  
       activate receive (poPOReceive.opPOReceive, msgPO);  
       send (poPOSend.opPOSend, msgPO);  
       }  
     }  
}  
```  
  
 上記の XLANG/s プログラムでは、XLANG/s プログラムのコンパイル単位を `module` キーワードで定義しています。 プログラムで使用されるすべての型: など**porttype**、 **correlationsettype**、 **servicelinktype**、および**messagetype**— スコープにはこのレベルです。  
  
 ポートは、xlang/s を送信または受信メッセージを送受信するコンストラクトであり、ポートと呼ばれる定義済みの型**porttype**です。 **Porttype**構成体は、ポートで使用できる操作のコレクションを定義します。 これらの操作は、ポート経由での単一の有効なメッセージ交換を定義します。 定義に**porttype**、 **messagetype**、 **servicelinktype**、または**correlationsettype**に xlang/s の作成者を構築します。基本的に、プログラムが複雑なデータの種類の定義を作成しています。 これらの定義に同じメリットが持っている場合は他の言語で複雑なデータ型: データ型の上位のレベルに組み込まれた概念が abstract であり、これにより、データ型の再利用が容易です。  
  
 **PtPOReceive**で上記の HelloWorldApp モジュールが、一方向で定義されているポートの受信ポート操作で**opPOReceive**です。 このサービスの HelloWorld ブロックでは、プロセスの実際の実装と、ポート変数やメッセージ変数などプロセスで使用される変数を定義しています。 このブロック内のコードの最初の 3 つの行がポートの変数を定義する**poPOReceive**と**poPOSend**メッセージ**msgPO**それぞれします。 本文には、サービスに渡すパラメーターと実行動作を表すコードが記述されています。 入れ子になったスコープ ブロックで定義されているものを除くすべての変数は、このレベルにスコープ設定されます。 アクティブ化受信である、receive ステートメントを受信、 **msgPO**からのメッセージ、 **poPOReceive.opPOReceive**ポートし、オーケストレーションの新しいインスタンスを作成します。 メッセージを受信した後、send ステートメントでそのメッセージを送信ポートに送信します。 上記のコードでは、2 つのポート宣言で**poPOReceive** implements 修飾子を使用しますが、 **poPOSend** uses 修飾子を使用します。 implements 修飾子は、そのポート経由でメッセージを受信することをランタイムに通知します。 uses 修飾子は、そのポート経由でメッセージを送信することをランタイムに通知します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XLANG のデータ型](../core/xlang-s-data-types.md)  
  
-   [XLANG のステートメント](../core/xlang-s-statements.md)  
  
-   [XLANG の変数および演算子](../core/xlang-s-variables-and-operators.md)  
  
-   [XLANG の式](../core/xlang-s-expressions.md)  
  
-   [XLANG s の予約語](../core/xlang-s-reserved-words.md)  
  
-   [XLANG-s BPEL4WS 型への変換から](../core/xlang-s-to-bpel4ws-type-conversions.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk オーケストレーション エンジンについて](../core/about-the-biztalk-orchestration-engine.md)