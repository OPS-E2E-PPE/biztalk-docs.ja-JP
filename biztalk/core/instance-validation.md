---
title: インスタンスの検証 |Microsoft Docs
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
ms.openlocfilehash: a76ae6dac1e095ac68c93477a3f3eafcfc170bff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382102"
---
# <a name="instance-validation"></a>インスタンスの検証
BizTalk エディターを起動、 **IInstanceValidator.ValidateInstance**メソッドの次の条件が満たされたときに、拡張機能。  
  
- 使用して、拡張機能が設定の標準として、**標準**のプロパティ、**スキーマ**ノード。  
  
- **プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられた、**インスタンスの出力の種類の生成**プロパティに設定されて**ネイティブです。**  
  
- **プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられた、**入力インスタンス ファイル名**プロパティが検証するインスタンス メッセージを含むファイルの名前に設定します。  
  
  指定されたファイル、**入力インスタンス ファイル名**プロパティがパラメーターとして渡される、 **IInstanceValidator.ValidateInstance**メソッド。  
  
  エラーが発生したエラー メッセージがの配列として返されます**IValidationInfo**オブジェクトとに表示される、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]タスク一覧 ウィンドウ。  
  
> [!NOTE]
>  スキーマにパターン ステートメントが含まれていて、ファイルに渡されます、 **ValidateInstance**メソッドは、対応するを使用して生成された**インスタンスの生成**コマンドをインスタンス メッセージに渡すことができません検証します。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターの拡張](../core/extending-biztalk-editor.md)