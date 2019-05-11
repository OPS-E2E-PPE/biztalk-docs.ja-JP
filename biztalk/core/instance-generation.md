---
title: インスタンスの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14060dca-5e14-474a-bf2c-4e8bc56e3c61
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4674c8ff852be6ab6bf9b217ad68fe4ac4c14333
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382090"
---
# <a name="instance-generation"></a><span data-ttu-id="7a3a6-102">インスタンスの生成</span><span class="sxs-lookup"><span data-stu-id="7a3a6-102">Instance Generation</span></span>
<span data-ttu-id="7a3a6-103">BizTalk エディターを起動、 **IInstanceGenerator.GenerateInstance**メソッドの次の条件が満たされたときに、拡張機能。</span><span class="sxs-lookup"><span data-stu-id="7a3a6-103">BizTalk Editor invokes the **IInstanceGenerator.GenerateInstance** method of an extension when the following conditions are met:</span></span>  
  
-   <span data-ttu-id="7a3a6-104">使用して、拡張機能が設定の標準として、**標準**のプロパティ、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="7a3a6-104">The extension is set as standard by using the **Standard** property of the **Schema** node.</span></span>  
  
-   <span data-ttu-id="7a3a6-105">**プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられた、**インスタンスの出力の種類の生成**プロパティに設定されて**ネイティブです。**</span><span class="sxs-lookup"><span data-stu-id="7a3a6-105">On the **Property Pages** dialog box associated with the schema, the **Generate Instance Output Type** property is set to **Native.**</span></span>  
  
-   <span data-ttu-id="7a3a6-106">**プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられた、**出力インスタンス ファイル名**プロパティが出力インスタンスに保存されるファイルの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="7a3a6-106">On the **Property Pages** dialog box associated with the schema, the **Output Instance Filename** property is set to the name of the file that the output instance will be saved to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a3a6-107">場合、**出力インスタンス ファイル名**プロパティが設定されていない、一時フォルダーに既定のファイル名は、生成されたインスタンス メッセージの使用およびへのリンクは、出力ウィンドウに提供されます。</span><span class="sxs-lookup"><span data-stu-id="7a3a6-107">If the **Output Instance Filename** property is not set, a default file name in a temporary folder is used for the generated instance message, and a link to it is provided in the Output window.</span></span>  
  
 <span data-ttu-id="7a3a6-108">前に、 **IInstanceValidator.ValidateInstance**ファイルで指定して、BizTalk エディターが、サンプル XML インスタンス メッセージを生成し、それを渡します、メソッドが呼び出されます、**出力インスタンス ファイル名**プロパティ、またはそのメソッドに既定のファイル名。</span><span class="sxs-lookup"><span data-stu-id="7a3a6-108">Before the **IInstanceValidator.ValidateInstance** method is called, BizTalk Editor generates a sample XML instance message, and then passes it and the file specified in the **Output Instance Filename** property, or a default file name, to that method.</span></span>  
  
 <span data-ttu-id="7a3a6-109">エラーが発生したエラー メッセージがの配列として返されます**IValidationInfo**オブジェクトとに表示される、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]タスク一覧 ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="7a3a6-109">If errors occur, error messages are returned as an array of **IValidationInfo** objects, and are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Task List window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a3a6-110">参照</span><span class="sxs-lookup"><span data-stu-id="7a3a6-110">See Also</span></span>  
 [<span data-ttu-id="7a3a6-111">BizTalk エディターの拡張</span><span class="sxs-lookup"><span data-stu-id="7a3a6-111">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)