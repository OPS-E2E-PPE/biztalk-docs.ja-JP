---
title: エラー抽出サンプル クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 53ceb305dcd30164e385022f66140fcaa626b133
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965128"
---
# <a name="error-extractor-sample-class"></a><span data-ttu-id="647df-102">エラー抽出サンプル クラス</span><span class="sxs-lookup"><span data-stu-id="647df-102">Error Extractor Sample Class</span></span>
<span data-ttu-id="647df-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]逆アセンブラーは、XML オブジェクトへのエラーをシリアル化し、マルチパート メッセージのエラー セクションに、XML オブジェクトをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="647df-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] disassembler serializes errors to an XML object, and attaches the XML object to the error section of a multipart message.</span></span> <span data-ttu-id="647df-104">逆アセンブラーは、有効なメッセージの場合と同様後、失敗したメッセージとメッセージ ボックス データベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="647df-104">The disassembler then publishes the failed message to the MessageBox database just as it would a valid message.</span></span> <span data-ttu-id="647df-105">そのため、メッセージ ボックス データベースにメッセージ carry エラーの詳細に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="647df-105">Therefore, failed messages carry error details into the MessageBox database.</span></span> <span data-ttu-id="647df-106">エラー抽出サンプル クラスを使用して、失敗したメッセージからエラーの詳細を抽出し、エラーの詳細を含む 1 つのファイルと元のメッセージを持つ別のファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="647df-106">You can use the Error Extractor Sample Class to extract the error details from a failed message, and generate one file that has the error details and another file that has the original message.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="647df-107">エラー抽出サンプル クラスは、SDK のサンプル コードです。</span><span class="sxs-lookup"><span data-stu-id="647df-107">The Error Extractor Sample Class is sample code in the SDK.</span></span> <span data-ttu-id="647df-108">実稼働環境で使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="647df-108">It is not intended for use in production.</span></span>  
  
 <span data-ttu-id="647df-109">エラー抽出サンプル クラスを使用するを失敗したメッセージを処理するオーケストレーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="647df-109">To use the Error Extractor Sample Class, you must create an orchestration to process the failed message.</span></span> <span data-ttu-id="647df-110">このオーケストレーションには、失敗したメッセージの本文を抽出、失敗したメッセージのエラーの一部を抽出、および本文と個別の XML ファイルにエラーの一部を次に、記述する手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="647df-110">This orchestration includes steps to extract the body of the failed message, extract the error part of the failed message, and then write the body and the error part to separate XML files.</span></span> <span data-ttu-id="647df-111">オーケストレーションは、エラー抽出サンプル クラスで、次の方法の 1 つ以上を呼び出す式段階でこれらの各手順を表します。</span><span class="sxs-lookup"><span data-stu-id="647df-111">The orchestration represents each of these steps in an expression stage that calls one or more of the following methods in the Error Extractor Sample Class:</span></span>  
  
## <a name="getbodypartasstring-method"></a><span data-ttu-id="647df-112">GetBodyPartAsString メソッド</span><span class="sxs-lookup"><span data-stu-id="647df-112">GetBodyPartAsString method</span></span>  
 <span data-ttu-id="647df-113">このメソッドは、'xm' XLANG メッセージのボディ部で検出された XML を格納する文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="647df-113">This method returns a string that contains the XML found in the body part of the XLANG message 'xm'.</span></span> <span data-ttu-id="647df-114">メソッドはボディ部を格納するには、XLANG メッセージ 'xm' が必要です"BodySegment"と呼ばれる</span><span class="sxs-lookup"><span data-stu-id="647df-114">The method expects the XLANG message 'xm' to contain a body part called "BodySegment."</span></span> <span data-ttu-id="647df-115">そのため、このボディ パーツの名前を持つ呼び出し元のオーケストレーションでは、' xm' を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="647df-115">Therefore, you must declare 'xm' in the calling orchestration with this body part name.</span></span> <span data-ttu-id="647df-116">'Xm' の一部として"BodySegment"が存在しない場合**GetBodyPartAsString**例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="647df-116">If "BodySegment" does not exist as a part of 'xm', **GetBodyPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a><span data-ttu-id="647df-117">GetErrorPartAsString メソッド</span><span class="sxs-lookup"><span data-stu-id="647df-117">GetErrorPartAsString method</span></span>  
 <span data-ttu-id="647df-118">このメソッドは、XML を格納する文字列、エラー メッセージの一部、XLANG 'xm' で見つかったを返します。</span><span class="sxs-lookup"><span data-stu-id="647df-118">This method returns a string that contains the XML found in the error part of the XLANG message 'xm'.</span></span> <span data-ttu-id="647df-119">メソッドが受け取るエラー部分を格納するには、XLANG メッセージ 'xm'"ErrorSegment"と呼ばれる</span><span class="sxs-lookup"><span data-stu-id="647df-119">The method expects the XLANG message 'xm' to contain an error part called "ErrorSegment."</span></span> <span data-ttu-id="647df-120">そのため、このエラーの一部の名前を持つ呼び出し元のオーケストレーションでは、' xm' を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="647df-120">Therefore, you must declare 'xm' in the calling orchestration with this error part name.</span></span> <span data-ttu-id="647df-121">'Xm' の一部として"ErrorSegment"が存在しない場合**GetErrorPartAsString**例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="647df-121">If "ErrorSegment" does not exist as a part of 'xm', **GetErrorPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a><span data-ttu-id="647df-122">WriteToFile メソッド</span><span class="sxs-lookup"><span data-stu-id="647df-122">WriteToFile method</span></span>  
 <span data-ttu-id="647df-123">このメソッドは、元の文字列を書き込みます、*メッセージ*パラメーターで指定されたファイルを*filePath*パラメーター。</span><span class="sxs-lookup"><span data-stu-id="647df-123">This method writes the string from the *message* parameter to the file specified by the *filePath* parameter.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 <span data-ttu-id="647df-124">A4SWIFT セットアップでは、エラー抽出サンプル クラス (SWIFTErrorExtractor.dll) をインストールに A4SWIFT SDK の一部として\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor です。</span><span class="sxs-lookup"><span data-stu-id="647df-124">A4SWIFT Setup installs the Error Extractor Sample Class (SWIFTErrorExtractor.dll) as part of the A4SWIFT SDK in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor.</span></span> <span data-ttu-id="647df-125">このフォルダーには、サンプル クラス (ErrorExtractor.cs) のソース コードも含まれています。</span><span class="sxs-lookup"><span data-stu-id="647df-125">This folder also includes the source code for the sample class (ErrorExtractor.cs).</span></span>  
  
 <span data-ttu-id="647df-126">オーケストレーションから呼び出す SWIFTErrorExtractor.dll には、グローバル アセンブリ キャッシュに .dll ファイルを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="647df-126">To call SWIFTErrorExtractor.dll from the orchestration, you must publish the .dll file to the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647df-127">参照</span><span class="sxs-lookup"><span data-stu-id="647df-127">See Also</span></span>  
 [<span data-ttu-id="647df-128">ツール</span><span class="sxs-lookup"><span data-stu-id="647df-128">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)