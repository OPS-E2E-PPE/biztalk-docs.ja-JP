---
title: "キャプチャおよび Message Repair ソリューションを拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages, errors
- code samples, errors
- errors, code sample
- repairing messages, code sample
- ErrorCollection objects
ms.assetid: 93f463a0-ecff-4f3e-a145-7c506f42c767
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb2f5fb1960a149c96a179ba596c67c9f402016
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="extending-the-solution-for-capture-and-message-repair"></a>キャプチャおよび Message Repair ソリューションを拡張します。
このヘルプに MT103 エンド ツー エンド チュートリアルでは、失敗した SWIFT メッセージをサブスクライブする BizTalk オーケストレーションを構築する方法を示します。  
  
 MT103 エンド ツー エンドのチュートリアルのオーケストレーションでは、ヘルパー クラスの静的メソッドを使用して**ErrorExtractor**エラーの部分と本文を文字列としてメッセージから抽出します。 オーケストレーションは、パーツを別のファイルを書き込みます。  
  
 失敗したメッセージのエラーの一部がのシリアル化であるため、**元**パイプライン コンポーネントによって構築された、コレクションを逆シリアル化して使用できますが、エラー報告および処理の多くを自動化します。 次[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]コードが失敗したメッセージのエラー メッセージの部分を逆シリアル化し、コレクション内の解析エラーを反復処理する方法を示しています。 コード フラグメントには、読みやすくするための名前空間の修飾を省略します。  
  
```  
// instantiate an appropriate XmlTextReader  
// xm contains the message  
string sError = ErrorExtractor.GetErrorPartAsString(xm);  
StringReader sRdr = new StringReader(sError);  
XmlTextReader xRdr = new XmlTextReader(sRdr);  
  
// deserialize the collection  
ErrorCollection eC = ErrorCollection.GetErrorCollection(xRdr);  
  
// loop over the parsing errors in the collection  
IEnumerator pEnum = eC.GetParseErrorEnumerator();  
while(pEnum.MoveNext())   
{  
  // pEnum.Current() returns a ParseError object for processing  
}  
  
```  
  
 **元**エラーによって、すべてのエラーのコレクションを反復処理する場合と同様に型を反復処理するためのメソッドが含まれています。 詳細については、**元**元のメンバーを参照してください。  
  
## <a name="see-also"></a>参照  
 [失敗したメッセージと元のオブジェクト](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)