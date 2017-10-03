---
title: "エラー抽出サンプル クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Error Extractor Sample class
- errors, Error Extractor Sample class
ms.assetid: d0d59b21-d80a-4466-a77a-1d3b7df1bc2a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0389f2fdb3f9ccb07bcc8ec9e4cdb1ec510927a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-extractor-sample-class"></a>エラー抽出サンプル クラス
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]逆アセンブラーは、XML オブジェクトへのエラーをシリアル化し、マルチパート メッセージのエラー セクションに、XML オブジェクトをアタッチします。 逆アセンブラーは、有効なメッセージの場合と同様後、失敗したメッセージとメッセージ ボックス データベースに公開します。 そのため、メッセージ ボックス データベースにメッセージ carry エラーの詳細に失敗しました。 エラー抽出サンプル クラスを使用して、失敗したメッセージからエラーの詳細を抽出し、エラーの詳細を含む 1 つのファイルと元のメッセージを持つ別のファイルを生成できます。  
  
> [!IMPORTANT]
>  エラー抽出サンプル クラスは、SDK のサンプル コードです。 実稼働環境で使用することはありません。  
  
 エラー抽出サンプル クラスを使用するを失敗したメッセージを処理するオーケストレーションを作成する必要があります。 このオーケストレーションには、失敗したメッセージの本文を抽出、失敗したメッセージのエラーの一部を抽出、および本文と個別の XML ファイルにエラーの一部を次に、記述する手順が含まれます。 オーケストレーションは、エラー抽出サンプル クラスで、次の方法の 1 つ以上を呼び出す式段階でこれらの各手順を表します。  
  
## <a name="getbodypartasstring-method"></a>GetBodyPartAsString メソッド  
 このメソッドは、'xm' XLANG メッセージのボディ部で検出された XML を格納する文字列を返します。 メソッドはボディ部を格納するには、XLANG メッセージ 'xm' が必要です"BodySegment"と呼ばれる そのため、このボディ パーツの名前を持つ呼び出し元のオーケストレーションでは、' xm' を宣言する必要があります。 'Xm' の一部として"BodySegment"が存在しない場合**GetBodyPartAsString**例外をスローします。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a>GetErrorPartAsString メソッド  
 このメソッドは、XML を格納する文字列、エラー メッセージの一部、XLANG 'xm' で見つかったを返します。 メソッドが受け取るエラー部分を格納するには、XLANG メッセージ 'xm'"ErrorSegment"と呼ばれる そのため、このエラーの一部の名前を持つ呼び出し元のオーケストレーションでは、' xm' を宣言する必要があります。 'Xm' の一部として"ErrorSegment"が存在しない場合**GetErrorPartAsString**例外をスローします。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a>WriteToFile メソッド  
 このメソッドは、元の文字列を書き込みます、*メッセージ*パラメーターで指定されたファイルを*filePath*パラメーター。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 A4SWIFT セットアップでは、エラー抽出サンプル クラス (SWIFTErrorExtractor.dll) をインストールに A4SWIFT SDK の一部として\<*ドライブ*>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor です。 このフォルダーには、サンプル クラス (ErrorExtractor.cs) のソース コードも含まれています。  
  
 オーケストレーションから呼び出す SWIFTErrorExtractor.dll には、グローバル アセンブリ キャッシュに .dll ファイルを発行する必要があります。  
  
## <a name="see-also"></a>参照  
 [ツール](../../adapters-and-accelerators/accelerator-swift/tools.md)