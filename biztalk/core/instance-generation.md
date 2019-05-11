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
# <a name="instance-generation"></a>インスタンスの生成
BizTalk エディターを起動、 **IInstanceGenerator.GenerateInstance**メソッドの次の条件が満たされたときに、拡張機能。  
  
-   使用して、拡張機能が設定の標準として、**標準**のプロパティ、**スキーマ**ノード。  
  
-   **プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられた、**インスタンスの出力の種類の生成**プロパティに設定されて**ネイティブです。**  
  
-   **プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられた、**出力インスタンス ファイル名**プロパティが出力インスタンスに保存されるファイルの名前に設定します。  
  
> [!NOTE]
>  場合、**出力インスタンス ファイル名**プロパティが設定されていない、一時フォルダーに既定のファイル名は、生成されたインスタンス メッセージの使用およびへのリンクは、出力ウィンドウに提供されます。  
  
 前に、 **IInstanceValidator.ValidateInstance**ファイルで指定して、BizTalk エディターが、サンプル XML インスタンス メッセージを生成し、それを渡します、メソッドが呼び出されます、**出力インスタンス ファイル名**プロパティ、またはそのメソッドに既定のファイル名。  
  
 エラーが発生したエラー メッセージがの配列として返されます**IValidationInfo**オブジェクトとに表示される、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]タスク一覧 ウィンドウ。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターの拡張](../core/extending-biztalk-editor.md)