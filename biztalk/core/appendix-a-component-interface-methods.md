---
title: "付録 a: コンポーネント インターフェイスのメソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, methods
- methods, component interfaces
- component interface methods
ms.assetid: c8377589-fbdf-4287-b822-53263a00381d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cb5b87cb063f22c889291b8eff3b2be50d64a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-a-component-interface-methods"></a>付録 a: コンポーネント インターフェイス メソッド
Microsoft BizTalk Adapter for PeopleSoft Enterprise は、コンポーネント インターフェイスの標準的なメソッドを提供します。  
  
> [!NOTE]
>  これらのメソッドの Ex バージョンで使用される `interactiveMode` パラメーターは、バックエンドに対する呼び出しのデバッグを補助します (`Create/CreateEx`、`Update/UpdateEx`、および `DeleteOnly`)。 内の各項目、* Ex、バックエンドの呼び出しと呼ばれるとは別に、どの項目が失敗しましただけを認識できるようにします。 使用するときにパフォーマンスの低下がある、 \*Ex メソッドの各プロパティの項目が別個の呼び出しを受信するためです。 開発できる\*Ex メソッドしに切り替えると、メイン メソッド (たとえば、 `Create`) 運用環境用です。 メソッドの使用を切り替える、実稼働環境にデバッグ スイッチを使用することもでき、 \*Ex メソッドです。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [CreateEx メソッド](../core/createex-method.md)  
  
-   [DeleteOnly メソッド](../core/deleteonly-method.md)  
  
-   [Find メソッド](../core/find-method.md)  
  
-   [Get メソッド](../core/get-method.md)  
  
-   [UpdateEx メソッド](../core/updateex-method.md)  
  
-   [コンポーネント インターフェイス ユーザー定義メソッド](../core/component-interface-user-defined-methods.md)  
  
-   [発効日のプロパティ](../core/effective-date-properties.md)