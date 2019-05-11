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
ms.openlocfilehash: 26375519e77de07161e20d9e373f2382cdbf0aac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378020"
---
# <a name="error-extractor-sample-class"></a><span data-ttu-id="ad3e1-102">エラー抽出サンプル クラス</span><span class="sxs-lookup"><span data-stu-id="ad3e1-102">Error Extractor Sample Class</span></span>
<span data-ttu-id="ad3e1-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]逆アセンブラーは、XML オブジェクトへのエラーをシリアル化し、マルチパート メッセージのエラーのセクションに、XML オブジェクトをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-103">The Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] disassembler serializes errors to an XML object, and attaches the XML object to the error section of a multipart message.</span></span> <span data-ttu-id="ad3e1-104">逆アセンブラーは、有効なメッセージと同様、失敗したメッセージとメッセージ ボックス データベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-104">The disassembler then publishes the failed message to the MessageBox database just as it would a valid message.</span></span> <span data-ttu-id="ad3e1-105">そのため、メッセージ ボックス データベースにメッセージの実行エラーの詳細に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-105">Therefore, failed messages carry error details into the MessageBox database.</span></span> <span data-ttu-id="ad3e1-106">エラー抽出サンプル クラスを使用して、失敗したメッセージからエラーの詳細を抽出し、エラーの詳細を含む 1 つのファイルと元のメッセージを持つ別のファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-106">You can use the Error Extractor Sample Class to extract the error details from a failed message, and generate one file that has the error details and another file that has the original message.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ad3e1-107">エラー抽出サンプル クラスは、SDK のサンプル コードです。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-107">The Error Extractor Sample Class is sample code in the SDK.</span></span> <span data-ttu-id="ad3e1-108">運用環境で使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-108">It is not intended for use in production.</span></span>  
  
 <span data-ttu-id="ad3e1-109">エラー抽出サンプル クラスを使用するには、失敗したメッセージを処理するオーケストレーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-109">To use the Error Extractor Sample Class, you must create an orchestration to process the failed message.</span></span> <span data-ttu-id="ad3e1-110">このオーケストレーションには、失敗したメッセージの本文を抽出、失敗したメッセージのエラーの一部を抽出し、本文と個別の XML ファイルにエラーの部分を記述する手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-110">This orchestration includes steps to extract the body of the failed message, extract the error part of the failed message, and then write the body and the error part to separate XML files.</span></span> <span data-ttu-id="ad3e1-111">オーケストレーションでは、エラー抽出サンプル クラスで 1 つ以上の次のメソッドを呼び出す式ステージでは、これらの各手順を表します。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-111">The orchestration represents each of these steps in an expression stage that calls one or more of the following methods in the Error Extractor Sample Class:</span></span>  
  
## <a name="getbodypartasstring-method"></a><span data-ttu-id="ad3e1-112">GetBodyPartAsString メソッド</span><span class="sxs-lookup"><span data-stu-id="ad3e1-112">GetBodyPartAsString method</span></span>  
 <span data-ttu-id="ad3e1-113">このメソッドは、'xm' XLANG メッセージのボディ部にある XML を含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-113">This method returns a string that contains the XML found in the body part of the XLANG message 'xm'.</span></span> <span data-ttu-id="ad3e1-114">メソッドにボディ部を格納するには、XLANG メッセージ 'xm' が必要ですが"BodySegment"と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-114">The method expects the XLANG message 'xm' to contain a body part called "BodySegment."</span></span> <span data-ttu-id="ad3e1-115">したがって、このボディ部の名前と呼び出し元のオーケストレーションには、' xm' を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-115">Therefore, you must declare 'xm' in the calling orchestration with this body part name.</span></span> <span data-ttu-id="ad3e1-116">'Xm' の一部として"BodySegment"が存在しない場合**GetBodyPartAsString**例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-116">If "BodySegment" does not exist as a part of 'xm', **GetBodyPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a><span data-ttu-id="ad3e1-117">GetErrorPartAsString メソッド</span><span class="sxs-lookup"><span data-stu-id="ad3e1-117">GetErrorPartAsString method</span></span>  
 <span data-ttu-id="ad3e1-118">このメソッドは、XLANG メッセージ 'xm' のエラーの部分にある XML を含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-118">This method returns a string that contains the XML found in the error part of the XLANG message 'xm'.</span></span> <span data-ttu-id="ad3e1-119">メソッドが受け取るエラーの部分を格納するには、XLANG メッセージ 'xm'"ErrorSegment"と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-119">The method expects the XLANG message 'xm' to contain an error part called "ErrorSegment."</span></span> <span data-ttu-id="ad3e1-120">したがって、このエラーの一部の名前を持つ呼び出し元のオーケストレーションには、' xm' を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-120">Therefore, you must declare 'xm' in the calling orchestration with this error part name.</span></span> <span data-ttu-id="ad3e1-121">'Xm' の一部として"ErrorSegment"が存在しない場合**GetErrorPartAsString**例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-121">If "ErrorSegment" does not exist as a part of 'xm', **GetErrorPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a><span data-ttu-id="ad3e1-122">WriteToFile メソッド</span><span class="sxs-lookup"><span data-stu-id="ad3e1-122">WriteToFile method</span></span>  
 <span data-ttu-id="ad3e1-123">このメソッドは、元の文字列を書き込みます、*メッセージ*パラメーターで指定されたファイルを*filePath*パラメーター。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-123">This method writes the string from the *message* parameter to the file specified by the *filePath* parameter.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 <span data-ttu-id="ad3e1-124">A4SWIFT セットアップでは、エラー抽出サンプル クラス (SWIFTErrorExtractor.dll) をインストールに A4SWIFT SDK の一部として\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor します。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-124">A4SWIFT Setup installs the Error Extractor Sample Class (SWIFTErrorExtractor.dll) as part of the A4SWIFT SDK in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor.</span></span> <span data-ttu-id="ad3e1-125">このフォルダーには、サンプル クラス (ErrorExtractor.cs) のソース コードも含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-125">This folder also includes the source code for the sample class (ErrorExtractor.cs).</span></span>  
  
 <span data-ttu-id="ad3e1-126">オーケストレーションから呼び出す SWIFTErrorExtractor.dll には、グローバル アセンブリ キャッシュに .dll ファイルを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad3e1-126">To call SWIFTErrorExtractor.dll from the orchestration, you must publish the .dll file to the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3e1-127">参照</span><span class="sxs-lookup"><span data-stu-id="ad3e1-127">See Also</span></span>  
 [<span data-ttu-id="ad3e1-128">ツール</span><span class="sxs-lookup"><span data-stu-id="ad3e1-128">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)