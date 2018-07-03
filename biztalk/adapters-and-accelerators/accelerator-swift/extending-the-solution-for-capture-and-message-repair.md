---
title: キャプチャおよびメッセージ修復のソリューションを拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages, errors
- code samples, errors
- errors, code sample
- repairing messages, code sample
- ErrorCollection objects
ms.assetid: 93f463a0-ecff-4f3e-a145-7c506f42c767
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc2b4436906b1df913deec8b525143773dd43e4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979643"
---
# <a name="extending-the-solution-for-capture-and-message-repair"></a>キャプチャおよびメッセージ修復のソリューションを拡張します。
このヘルプに MT103 エンド ツー エンドのチュートリアルでは、失敗した SWIFT メッセージをサブスクライブする BizTalk オーケストレーションを構築する方法を示します。  
  
 MT103 エンド ツー エンドのチュートリアルのオーケストレーションでは、ヘルパー クラスの静的メソッドを使用して**ErrorExtractor**をエラーの部分と本文を文字列としてメッセージから抽出します。 オーケストレーションは、個別のファイルの部分を書き込みます。  
  
 失敗したメッセージのエラーの一部がのシリアル化であるため、 **ErrorCollection**パイプライン コンポーネントによって構築された、コレクションを逆シリアル化して使用できますが、エラー報告と処理の多くを自動化します。 次の Microsoft[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]のコードが失敗したメッセージのエラー メッセージの部分を逆シリアル化し、コレクション内の解析エラーを反復処理する方法を示しています。 コード フラグメントは、読みやすくするための名前空間の修飾が省略されます。  
  
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
  
 **ErrorCollection**エラーによって、すべてのコレクション内のエラーを反復処理する場合と同様に型を反復処理するメソッドが含まれます。 詳細については、 **ErrorCollection**元のメンバーを参照してください。  
  
## <a name="see-also"></a>参照  
 [失敗したメッセージと ErrorCollection オブジェクト](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)