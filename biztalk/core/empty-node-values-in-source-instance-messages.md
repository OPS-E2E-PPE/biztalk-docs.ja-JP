---
title: インスタンス メッセージのソース内の空のノードの値 |Microsoft Docs
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
ms.openlocfilehash: afaf714e3c979576939ebef8fdd39f283828cab7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350017"
---
# <a name="empty-node-values-in-source-instance-messages"></a><span data-ttu-id="2bec7-102">送信元インスタンス メッセージの空のノードの値</span><span class="sxs-lookup"><span data-stu-id="2bec7-102">Empty Node Values in Source Instance Messages</span></span>
<span data-ttu-id="2bec7-103">マップをテストするとき、必ずしもすべてのスキーマ ノードの内容が必要になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2bec7-103">There may be times when you do not want content in all of the schema nodes when you test a map.</span></span>  

## <a name="ceate-empty-node-values"></a><span data-ttu-id="2bec7-104">作成の空のノードの値</span><span class="sxs-lookup"><span data-stu-id="2bec7-104">Ceate empty node values</span></span>  

1. <span data-ttu-id="2bec7-105">BizTalk エディターを使用してインスタンス データを生成します。</span><span class="sxs-lookup"><span data-stu-id="2bec7-105">Generate instance data using BizTalk Editor.</span></span> <span data-ttu-id="2bec7-106">インスタンス データ生成の詳細については、次を参照してください。[インスタンス メッセージの生成方法](../core/how-to-generate-instance-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="2bec7-106">For more information about generating instance data, see [How to Generate Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  

2. <span data-ttu-id="2bec7-107">テキスト エディターで入力インスタンス メッセージを開き、空にする対象の要素と属性からデータを削除し、変更したインスタンス ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="2bec7-107">Open the input instance message in a text editor, delete the data from elements and attributes that you want to be empty, and then save the modified instance file.</span></span>  

3. <span data-ttu-id="2bec7-108">スキーマの検証やテストの実行時に、変更したファイルが使用されるよう、BizTalk マッパーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2bec7-108">Configure BizTalk Mapper to use the file you just modified when the schema is validated and tested.</span></span> <span data-ttu-id="2bec7-109">スキーマのプロパティ ウィンドウでファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="2bec7-109">You set the file in the Properties window for the schema.</span></span> <span data-ttu-id="2bec7-110">プロパティの設定の詳細については、次を参照してください。**マップ ファイル プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2bec7-110">For more information about setting properties, see **Map File Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="2bec7-111">参照</span><span class="sxs-lookup"><span data-stu-id="2bec7-111">See Also</span></span>  
- [<span data-ttu-id="2bec7-112">インスタンス メッセージを生成する方法</span><span class="sxs-lookup"><span data-stu-id="2bec7-112">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)   
- <span data-ttu-id="2bec7-113">**スキーマ プロパティのリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2bec7-113">**Schema Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
