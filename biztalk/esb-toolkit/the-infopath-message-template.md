---
title: "メッセージの InfoPath テンプレート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bb055b1-8480-44dd-8739-f2981bca63c3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b8ec04d16da25f39060540aa8a8205421397d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-infopath-message-template"></a>InfoPath メッセージ テンプレート
ESB の管理ポータルで ESB フォールト メッセージを表示する代わりに、ユーザーの利用できますで提供される、ESB 例外メッセージ ビューアーをという名前の Microsoft InfoPath メッセージ テンプレート、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 ESB 例外管理フレームワークは、ESB 例外メッセージ ビューアー テンプレートと共に表示されるエラー メッセージと元のメッセージが含まれているいくつかのビューをシリアル化された形式でメッセージを保持できます。 ESB 例外メッセージ ビューアーには、次のビューが用意されています。  
  
-   全般ビュー  
  
-   例外オブジェクトの表示  
  
-   メッセージ ビュー  
  
 図 1 は、例外の最もアンビエント プロパティを表示する ESB 例外メッセージ ビューアーの [全般] ビューを示します。  
  
 ![例外メッセージの全般ビュー](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4 ExceptionMessageGeneralView")  
  
 **図 1**  
  
 **[全般] ビューを表示、ESB 例外メッセージ ビューアー**  
  
 図 2 は、例外オブジェクト ビューのプロパティとからスタック トレースが表示されます、 **System.Exception**オブジェクト。  
  
 ![例外メッセージ、例外オブジェクト](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4 ExceptionMessageExceptionObject")  
  
 **図 2**  
  
 **例外オブジェクトのビューを表示、ESB 例外メッセージ ビューアー**  
  
 図 3 は、元のユーザーが使用可能な永続化されたメッセージから選択できるドロップダウン リストを提供するメッセージ ビューを示します。 ビューには、永続化されたメッセージと XML メッセージの内容のコンテキスト プロパティの値が表示されます。  
  
 ![例外、メッセージのメッセージ ビュー](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4 ExceptionMessageMessagesView")  
  
 **図 3**  
  
 **メッセージ ビューを表示、ESB 例外メッセージ ビューアー**