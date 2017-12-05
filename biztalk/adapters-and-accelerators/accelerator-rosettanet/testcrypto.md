---
title: "TestCrypto |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, TestCrypto utility
- troubleshooting, TestCrypto utility
- TestCrypto utility
ms.assetid: 02768794-64ac-4d99-930c-738bed9626c5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 632ad57a8bb8a32c8f579a07980480dbd3bf0087
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="testcrypto"></a><span data-ttu-id="605fa-102">TestCrypto</span><span class="sxs-lookup"><span data-stu-id="605fa-102">TestCrypto</span></span>
<span data-ttu-id="605fa-103">TestCrypto ユーティリティを使用して、メッセージの暗号化解除に関連するトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="605fa-103">You use the TestCrypto utility to troubleshoot failures in decrypting messages.</span></span> <span data-ttu-id="605fa-104">このユーティリティは、暗号化の解除に失敗したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="605fa-104">The utility indicates whether decryption fails.</span></span> <span data-ttu-id="605fa-105">暗号化の解除が成功した場合は、証明書が何かが示され、暗号化が解除されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="605fa-105">If the decryption succeeds, the utility indicates what the certificate is, and displays the decrypted message.</span></span>  
  
 <span data-ttu-id="605fa-106">メッセージの暗号化された部分だけを含むファイル (暗号化されていないヘッダーを除く) に対して TestCrypto を実行します。</span><span class="sxs-lookup"><span data-stu-id="605fa-106">You run TestCrypto on a file that contains only the encrypted part of the message, without unencrypted headers.</span></span> <span data-ttu-id="605fa-107">受信メッセージをスニッフィングするか、`MessageStorageIn` からメッセージを取得して、メッセージの暗号化されたバイナリ ラージ オブジェクト (BLOB) をテキスト ファイルに抽出します。</span><span class="sxs-lookup"><span data-stu-id="605fa-107">Extract the encrypted binary large object (BLOB) from the message into a text file, either by sniffing the incoming message or by retrieving the message from `MessageStorageIn`.</span></span>  
  
 <span data-ttu-id="605fa-108">メッセージの取得の詳細については`MessageStorageIn`を参照してください[GetMessages サンプル](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="605fa-108">For more information about retrieving a message from `MessageStorageIn`, see [GetMessages Sample](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md).</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="605fa-109">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="605fa-109">Location in SDK</span></span>  
 <span data-ttu-id="605fa-110">\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk</span><span class="sxs-lookup"><span data-stu-id="605fa-110">\<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-testcrypto"></a><span data-ttu-id="605fa-111">TestCrypto の実行</span><span class="sxs-lookup"><span data-stu-id="605fa-111">Running TestCrypto</span></span>  
  
#### <a name="to-run-testcrypto"></a><span data-ttu-id="605fa-112">TestCrypto を実行するには</span><span class="sxs-lookup"><span data-stu-id="605fa-112">To run TestCrypto</span></span>  
  
1.  <span data-ttu-id="605fa-113">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリック**コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="605fa-113">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="605fa-114">移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk です。</span><span class="sxs-lookup"><span data-stu-id="605fa-114">Move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span>  
  
3.  <span data-ttu-id="605fa-115">コマンド プロンプトで次のように入力します。 **TestCrypto.exe \<filename\>**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="605fa-115">At the command prompt, type **TestCrypto.exe \<filename\>**, and then press ENTER.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="605fa-116">解説</span><span class="sxs-lookup"><span data-stu-id="605fa-116">Remarks</span></span>  
 <span data-ttu-id="605fa-117">ユーティリティが検出した証明書が適切な証明書ではない場合や無効な証明書である場合、または証明書が検出されない場合、暗号化の解除は失敗します。</span><span class="sxs-lookup"><span data-stu-id="605fa-117">Decryption fails if the certificate that the utility finds is not the required and valid certificate, or if the utility cannot find the certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605fa-118">参照</span><span class="sxs-lookup"><span data-stu-id="605fa-118">See Also</span></span>  
 [<span data-ttu-id="605fa-119">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="605fa-119">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)