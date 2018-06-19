---
title: インスタンスの検証 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f906f2e9-2bf9-448b-927f-dd2d7d9b2272
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3db1903030bbde96f2587ac14b5d168345b31823
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257378"
---
# <a name="instance-validation"></a>インスタンスの検証
BizTalk エディターを起動、 **IInstanceValidator.ValidateInstance**次の条件が満たされたときに、拡張機能のメソッド。  
  
-   使用して、拡張機能が設定の標準として、**標準**のプロパティ、**スキーマ**ノード。  
  
-   **プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられている、**インスタンスの出力の種類の生成**プロパティに設定されている**ネイティブです。**  
  
-   **プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられている、**入力インスタンス ファイル名**プロパティが検証に使用するインスタンス メッセージを含むファイルの名前に設定します。  
  
 指定されたファイル、**入力インスタンス ファイル名**プロパティにパラメーターとして渡される、 **IInstanceValidator.ValidateInstance**メソッドです。  
  
 配列としてエラーが発生した場合のエラー メッセージが返されます**IValidationInfo**オブジェクト、およびに表示される、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]タスク一覧ウィンドウ。  
  
> [!NOTE]
>  ファイルが渡された場合、スキーマにパターン ステートメントが含まれています、 **ValidateInstance**メソッドは、対応するを使用して生成された**インスタンスの生成**コマンドをインスタンス メッセージを渡すことがありますいません。検証します。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターの拡張](../core/extending-biztalk-editor.md)