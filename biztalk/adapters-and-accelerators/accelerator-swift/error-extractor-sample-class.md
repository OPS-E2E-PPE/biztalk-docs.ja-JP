---
title: エラー抽出サンプル クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Error Extractor Sample class
- errors, Error Extractor Sample class
ms.assetid: d0d59b21-d80a-4466-a77a-1d3b7df1bc2a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1085af05221b252bb6942e2c32bbe1f91c8d7688
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010771"
---
# <a name="error-extractor-sample-class"></a>エラー抽出サンプル クラス
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]逆アセンブラーは、XML オブジェクトへのエラーをシリアル化し、マルチパート メッセージのエラーのセクションに、XML オブジェクトをアタッチします。 逆アセンブラーは、有効なメッセージと同様、失敗したメッセージとメッセージ ボックス データベースに公開します。 そのため、メッセージ ボックス データベースにメッセージの実行エラーの詳細に失敗しました。 エラー抽出サンプル クラスを使用して、失敗したメッセージからエラーの詳細を抽出し、エラーの詳細を含む 1 つのファイルと元のメッセージを持つ別のファイルを生成できます。  
  
> [!IMPORTANT]
>  エラー抽出サンプル クラスは、SDK のサンプル コードです。 運用環境で使用するためのものではありません。  
  
 エラー抽出サンプル クラスを使用するには、失敗したメッセージを処理するオーケストレーションを作成する必要があります。 このオーケストレーションには、失敗したメッセージの本文を抽出、失敗したメッセージのエラーの一部を抽出し、本文と個別の XML ファイルにエラーの部分を記述する手順が含まれています。 オーケストレーションでは、エラー抽出サンプル クラスで 1 つ以上の次のメソッドを呼び出す式ステージでは、これらの各手順を表します。  
  
## <a name="getbodypartasstring-method"></a>GetBodyPartAsString メソッド  
 このメソッドは、'xm' XLANG メッセージのボディ部にある XML を含む文字列を返します。 メソッドにボディ部を格納するには、XLANG メッセージ 'xm' が必要ですが"BodySegment"と呼ばれる。 したがって、このボディ部の名前と呼び出し元のオーケストレーションには、' xm' を宣言する必要があります。 'Xm' の一部として"BodySegment"が存在しない場合**GetBodyPartAsString**例外をスローします。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a>GetErrorPartAsString メソッド  
 このメソッドは、XLANG メッセージ 'xm' のエラーの部分にある XML を含む文字列を返します。 メソッドが受け取るエラーの部分を格納するには、XLANG メッセージ 'xm'"ErrorSegment"と呼ばれる。 したがって、このエラーの一部の名前を持つ呼び出し元のオーケストレーションには、' xm' を宣言する必要があります。 'Xm' の一部として"ErrorSegment"が存在しない場合**GetErrorPartAsString**例外をスローします。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a>WriteToFile メソッド  
 このメソッドは、元の文字列を書き込みます、*メッセージ*パラメーターで指定されたファイルを*filePath*パラメーター。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 A4SWIFT セットアップでは、エラー抽出サンプル クラス (SWIFTErrorExtractor.dll) をインストールに A4SWIFT SDK の一部として\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor します。 このフォルダーには、サンプル クラス (ErrorExtractor.cs) のソース コードも含まれています。  
  
 オーケストレーションから呼び出す SWIFTErrorExtractor.dll には、グローバル アセンブリ キャッシュに .dll ファイルを発行する必要があります。  
  
## <a name="see-also"></a>参照  
 [ツール](../../adapters-and-accelerators/accelerator-swift/tools.md)