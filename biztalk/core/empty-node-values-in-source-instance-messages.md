---
title: インスタンス メッセージのソースで空のノードの値 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76f9d7c8-5a82-41e9-9077-7b1ddd80a837
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2a36271f5e9d66efc8ef0c50cdc9582f4de1261
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240082"
---
# <a name="empty-node-values-in-source-instance-messages"></a><span data-ttu-id="adae8-102">送信元インスタンス メッセージの空のノードの値</span><span class="sxs-lookup"><span data-stu-id="adae8-102">Empty Node Values in Source Instance Messages</span></span>
<span data-ttu-id="adae8-103">マップをテストするとき、必ずしもすべてのスキーマ ノードの内容が必要になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="adae8-103">There may be times when you do not want content in all of the schema nodes when you test a map.</span></span>  
  
## <a name="ceate-empty-node-values"></a><span data-ttu-id="adae8-104">空のノードの値</span><span class="sxs-lookup"><span data-stu-id="adae8-104">Ceate empty node values</span></span>  
  
1.  <span data-ttu-id="adae8-105">BizTalk エディターを使用してインスタンス データを生成します。</span><span class="sxs-lookup"><span data-stu-id="adae8-105">Generate instance data using BizTalk Editor.</span></span> <span data-ttu-id="adae8-106">インスタンス データ生成の詳細については、次を参照してください。[インスタンス メッセージの生成方法](../core/how-to-generate-instance-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="adae8-106">For more information about generating instance data, see [How to Generate Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
2.  <span data-ttu-id="adae8-107">テキスト エディターで入力インスタンス メッセージを開き、空にする対象の要素と属性からデータを削除し、変更したインスタンス ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="adae8-107">Open the input instance message in a text editor, delete the data from elements and attributes that you want to be empty, and then save the modified instance file.</span></span>  
  
3.  <span data-ttu-id="adae8-108">スキーマの検証やテストの実行時に、変更したファイルが使用されるよう、BizTalk マッパーを構成します。</span><span class="sxs-lookup"><span data-stu-id="adae8-108">Configure BizTalk Mapper to use the file you just modified when the schema is validated and tested.</span></span> <span data-ttu-id="adae8-109">スキーマのプロパティ ウィンドウでファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="adae8-109">You set the file in the Properties window for the schema.</span></span> <span data-ttu-id="adae8-110">プロパティの設定の詳細については、次を参照してください。**マップ ファイル プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="adae8-110">For more information about setting properties, see **Map File Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="adae8-111">参照</span><span class="sxs-lookup"><span data-stu-id="adae8-111">See Also</span></span>  
-  [<span data-ttu-id="adae8-112">インスタンス メッセージを生成する方法</span><span class="sxs-lookup"><span data-stu-id="adae8-112">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)   
-  <span data-ttu-id="adae8-113">**スキーマ プロパティのリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="adae8-113">**Schema Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>