---
title: "インスタンスの生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14060dca-5e14-474a-bf2c-4e8bc56e3c61
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bd3d2bc6852ec0c73fbbe4ffc55924a8012ce5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instance-generation"></a>インスタンスの生成
BizTalk エディターを起動、 **IInstanceGenerator.GenerateInstance**次の条件が満たされたときに、拡張機能のメソッド。  
  
-   使用して、拡張機能が設定の標準として、**標準**のプロパティ、**スキーマ**ノード。  
  
-   **プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられている、**インスタンスの出力の種類の生成**プロパティに設定されている**ネイティブです。**  
  
-   **プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられている、**出力インスタンス ファイル名**プロパティが、出力インスタンスに保存されるファイルの名前に設定します。  
  
> [!NOTE]
>  場合、**出力インスタンス ファイル名**プロパティが設定されていない、一時フォルダーの既定のファイル名が生成されたインスタンス メッセージの使用およびへのリンクは、出力ウィンドウに提供します。  
  
 前に、 **IInstanceValidator.ValidateInstance**で指定されたファイルと、BizTalk エディターは、サンプル XML インスタンス メッセージを生成し、それを渡しますメソッドが呼び出される、**出力インスタンス ファイル名**プロパティ、またはそのメソッドに、既定のファイル名。  
  
 配列としてエラーが発生した場合のエラー メッセージが返されます**IValidationInfo**オブジェクト、およびに表示される、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]タスク一覧ウィンドウ。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターの拡張](../core/extending-biztalk-editor.md)