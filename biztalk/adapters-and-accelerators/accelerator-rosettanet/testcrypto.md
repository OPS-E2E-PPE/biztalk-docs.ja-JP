---
title: TestCrypto |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, TestCrypto utility
- troubleshooting, TestCrypto utility
- TestCrypto utility
ms.assetid: 02768794-64ac-4d99-930c-738bed9626c5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 881cd9ee8729a18f5829490e42c0795aa1267e43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280516"
---
# <a name="testcrypto"></a><span data-ttu-id="fcd84-102">TestCrypto</span><span class="sxs-lookup"><span data-stu-id="fcd84-102">TestCrypto</span></span>
<span data-ttu-id="fcd84-103">TestCrypto ユーティリティを使用して、メッセージの暗号化解除エラーのトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="fcd84-103">You use the TestCrypto utility to troubleshoot failures in decrypting messages.</span></span> <span data-ttu-id="fcd84-104">このユーティリティは、復号化が失敗したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fcd84-104">The utility indicates whether decryption fails.</span></span> <span data-ttu-id="fcd84-105">ユーティリティには、証明書を通知し、表示することを示します、復号化が成功すると、復号化されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="fcd84-105">If the decryption succeeds, the utility indicates what the certificate is, and displays the decrypted message.</span></span>  
  
 <span data-ttu-id="fcd84-106">TestCrypto を実行するには、暗号化されていないヘッダー メッセージの暗号化された部分だけを含むファイルにします。</span><span class="sxs-lookup"><span data-stu-id="fcd84-106">You run TestCrypto on a file that contains only the encrypted part of the message, without unencrypted headers.</span></span> <span data-ttu-id="fcd84-107">受信メッセージをスニッフィングするかからのメッセージを取得することによって、テキスト ファイルにメッセージから暗号化されたバイナリ ラージ オブジェクト (BLOB) を抽出`MessageStorageIn`します。</span><span class="sxs-lookup"><span data-stu-id="fcd84-107">Extract the encrypted binary large object (BLOB) from the message into a text file, either by sniffing the incoming message or by retrieving the message from `MessageStorageIn`.</span></span>  
  
 <span data-ttu-id="fcd84-108">メッセージの取得の詳細については`MessageStorageIn`を参照してください[GetMessages サンプル](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="fcd84-108">For more information about retrieving a message from `MessageStorageIn`, see [GetMessages Sample](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md).</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="fcd84-109">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="fcd84-109">Location in SDK</span></span>  
 <span data-ttu-id="fcd84-110">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span><span class="sxs-lookup"><span data-stu-id="fcd84-110">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-testcrypto"></a><span data-ttu-id="fcd84-111">TestCrypto の実行</span><span class="sxs-lookup"><span data-stu-id="fcd84-111">Running TestCrypto</span></span>  
  
#### <a name="to-run-testcrypto"></a><span data-ttu-id="fcd84-112">TestCrypto を実行するには</span><span class="sxs-lookup"><span data-stu-id="fcd84-112">To run TestCrypto</span></span>  
  
1.  <span data-ttu-id="fcd84-113">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="fcd84-113">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="fcd84-114">移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk します。</span><span class="sxs-lookup"><span data-stu-id="fcd84-114">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span>  
  
3.  <span data-ttu-id="fcd84-115">コマンド プロンプトで「 **TestCrypto.exe \<filename\>** し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fcd84-115">At the command prompt, type **TestCrypto.exe \<filename\>**, and then press ENTER.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcd84-116">コメント</span><span class="sxs-lookup"><span data-stu-id="fcd84-116">Remarks</span></span>  
 <span data-ttu-id="fcd84-117">復号化は、ユーティリティが検出される証明書が必要な有効な証明書ではない場合、または証明書が見つからない場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="fcd84-117">Decryption fails if the certificate that the utility finds is not the required and valid certificate, or if the utility cannot find the certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd84-118">参照</span><span class="sxs-lookup"><span data-stu-id="fcd84-118">See Also</span></span>  
 [<span data-ttu-id="fcd84-119">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="fcd84-119">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
