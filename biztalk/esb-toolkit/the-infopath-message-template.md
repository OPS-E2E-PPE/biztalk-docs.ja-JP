---
title: InfoPath メッセージ テンプレート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb055b1-8480-44dd-8739-f2981bca63c3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8972c27a433755a922cdc1d5074902e412a46602
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399746"
---
# <a name="the-infopath-message-template"></a>InfoPath メッセージ テンプレート
ESB 管理ポータルで ESB エラー メッセージを表示する代わりに、ユーザーを利用して Microsoft InfoPath メッセージ テンプレートが付属、ESB 例外メッセージ ビューアーを名前付きの[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
 ESB 例外管理フレームワークは、ESB 例外メッセージ ビューアー テンプレートと共に、エラー メッセージの元のメッセージが含まれているいくつかのビューが表示されますが、シリアル化された形式でメッセージを保持できます。 ESB 例外のメッセージ ビューアーには、次のビューが用意されています。  
  
- [全般] ビュー  
  
- 例外オブジェクトのビュー  
  
- メッセージ ビュー  
  
  図 1 は、例外の最もアンビエント プロパティを表示する ESB 例外メッセージ ビューアの [全般] ビューを示します。  
  
  ![例外メッセージの全般ビュー](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4 ExceptionMessageGeneralView")  
  
  **図 1**  
  
  **[全般] ビューを表示、ESB 例外メッセージ ビューアー**  
  
  図 2 は、プロパティとからのスタック トレースを表示する例外オブジェクトのビューを示しています、 **System.Exception**オブジェクト。  
  
  ![例外メッセージ、例外オブジェクト](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4 ExceptionMessageExceptionObject")  
  
  **図 2**  
  
  **例外オブジェクトのビューを表示、ESB 例外メッセージ ビューアー**  
  
  図 3 は、元となる、ユーザーは、使用可能な永続化されたメッセージから選択できるドロップダウン リストを提供するメッセージ ビューを示します。 ビューには、永続化されたメッセージと XML メッセージの内容のコンテキスト プロパティの値が表示されます。  
  
  ![例外のメッセージのメッセージ ビュー](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4 ExceptionMessageMessagesView")  
  
  **図 3**  
  
  **メッセージ ビューを表示、ESB 例外メッセージ ビューアー**