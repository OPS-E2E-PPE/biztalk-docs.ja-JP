---
title: Xlang-s 言語 |Microsoft Docs
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
ms.openlocfilehash: 0b04a28390546e4e22e5f293d772f88371f76696
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394727"
---
# <a name="xlang-s-language"></a>Xlang-s 言語
Xlang/s では、XML、XSD、および Web サービス記述言語 (WSDL) などのインターネット標準を使用するように設計され、操作するためのサポートが組み込まれています。NET ベースのオブジェクトとメッセージです。 一部の式の機能を備えたメッセージング言語として XLANG/秒を表示できますC#します。 ただし、コードは xlang/s の間で移植性とC#します。  
  
 XLANG/秒では、プロセスと実装が明確に分離を促進します。 たとえば、ビジネス プロセスまたはプロトコル xlang/s で指定され、他の .NET プログラミング言語などに、ローカル データベースへのアクセスなど、アプリケーションの側面が実装されてC#または Visual Basic.NET します。  
  
 XLANG/秒の割り当てと式の構文については、裏付けC#を参照する必要があります、C#正確な構文の仕様。 XLANG/秒では、ビジネス プロセスの定義に使用される高レベルの構造の豊富なセットを定義します。 Xlang/s では、文字列や整数などの低レベルのデータ型をサポートして、高度なデータ型も定義されています。 メッセージ、ポート、相関関係、およびサービスへのリンク。 これらのデータ型は、ビジネス プロセスに関連付けられているセマンティクスを厳密に定義を使用して行い、プロセスによって補完されます制御ステートメントなど**中**または**スコープ**します。  
  
 Xlang/s ステートメントは一般に 2 つのカテゴリのいずれかに分類されますなど、自身で動作する単純なステートメント**受信**または**送信**、と複雑なステートメントを含むまたはいずれかの単純なステートメントをグループ化または。他の複合ステートメントなど**スコープ**、**並列**、および**リッスン**します。 Xlang/s に組み込まれているセマンティクスは、ビジネス プロセスのセマンティクスの定義については、Microsoft、IBM、および BEA によって公開されている Web Services (BPEL4WS) 仕様の Business Process Execution Language で定義されているのです。  
  
 BizTalk オーケストレーション デザイナーでオーケストレーション ダイアグラムの描画の結果として生成されるため、xlang/s の主な構造を理解することもあります。 オーケストレーション デザイナーは、ビジネス プロセスを視覚的に設計するための豊富なグラフィカル ツールです。 Xlang/s ファイルを .odx という拡張子を持ち、ヘッダーの追加のビジュアル情報と、本文にカスタム属性情報が含まれますが生成されます。  
  
> [!NOTE]
>  Xlang/s 言語は、専用なっています。 このセクションでは、オーケストレーションを開発する際に注意する必要があります言語の特定の部分を公開します。 .Odx ファイルの直接的な変更はサポートされていません。  
  
## <a name="xlangs-programs"></a>Xlang/s プログラム  
 最も単純な xlang/s プログラムでは、メッセージの種類が定義されている必要があります、オーケストレーションを付与する操作を開始するデータの一部です。 オーケストレーションでは、ポート経由でメッセージを受信し、し終了します。 次のコード例に示します。  
  
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
  
 上記の xlang/s プログラムで、`module`キーワードは、xlang/s プログラムのコンパイル単位を定義します。 プログラムで使用されるすべての型: など**porttype**、 **correlationsettype**、 **servicelinktype**、および**messagetype**— でスコープが設定このレベルです。  
  
 ポートとは、xlang/s が送信または受信メッセージを送受信するコンストラクトと、ポートと呼ばれる定義済みの型には**porttype**します。 **Porttype**構成体は、ポートで使用できる操作のコレクションを定義します。 これらの操作は、ポート経由で、1 つの有効なメッセージ交換を定義します。 定義する**porttype**、 **messagetype**、 **servicelinktype**、または**correlationsettype**に xlang/s の作成者を構築します。基本的に、プログラムが複雑なデータの種類の定義を作成しています。 これらの定義では、複合データ型と他の言語で同様に同じ利点があります。データ型の上位のレベルに組み込まれている概念を抽象化され、データ型を簡単に再利用可能になります。  
  
 **PtPOReceive**で上記の HelloWorldApp モジュールが一方向で定義されているポートの受信ポート操作で**opPOReceive**します。 サービスの HelloWorld ブロックでは、プロセス、ポートとメッセージ変数を含め、使用される任意の変数の実際の実装を定義します。 このブロック内のコードの最初の 3 つの行は、ポートの変数を定義**poPOReceive**と**poPOSend**メッセージ**msgPO**それぞれします。 本文には、サービス、および実行の動作へのパラメーターを記述するコードが含まれています。 すべての変数を入れ子になったスコープ ブロックで定義されていない場合は、このレベルにスコープされます。 アクティブ化受信である、receive ステートメントを受信、 **msgPO**からのメッセージ、 **poPOReceive.opPOReceive**ポートし、オーケストレーションの新しいインスタンスを作成します。 メッセージを受信すると、後に、send ステートメントは、送信ポートにメッセージを指示します。 上記のコードでは、2 つのポート宣言で**poPOReceive** implements 修飾子を使用しますが、 **poPOSend** uses 修飾子を使用します。 Implements 修飾子は、そのポート経由でメッセージを受信するには、ランタイムに指示します。 Uses 修飾子は、メッセージが送信ポート経由ですることをランタイムに指示します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XLANG-s データ型](../core/xlang-s-data-types.md)  
  
-   [XLANG-s ステートメント](../core/xlang-s-statements.md)  
  
-   [XLANG-s の変数および演算子](../core/xlang-s-variables-and-operators.md)  
  
-   [XLANG-s 式](../core/xlang-s-expressions.md)  
  
-   [XLANG-s の予約語](../core/xlang-s-reserved-words.md)  
  
-   [XLANG-s から BPEL4WS への種類の変換](../core/xlang-s-to-bpel4ws-type-conversions.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk オーケストレーション エンジンについて](../core/about-the-biztalk-orchestration-engine.md)