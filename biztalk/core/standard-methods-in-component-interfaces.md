---
title: コンポーネント インターフェイスの標準メソッド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, standard methods
- methods, viewing
- methods, component interfaces
- methods, changing
ms.assetid: 2273d946-3fc8-4b2d-a6a1-9e4f0da74d5b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eecb56f262a56e6567b44b146c631542cb1ceda6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994827"
---
# <a name="standard-methods-in-component-interfaces"></a>コンポーネント インターフェイスの標準メソッド
コンポーネント インターフェイスの標準メソッドを次に示します。  
  
- `Create`  
  
- `Find`  
  
- `Get`  
  
- `Save`  
  
  使用できるのは、基になるコンポーネントに含まれている上記のメソッドだけです。 たとえば、基になるコンポーネントに `Add` 機能が含まれていない場合、`Create` は使用できません。  
  
## <a name="viewing-or-changing-available-methods"></a>使用可能なメソッドの表示または変更  
  
#### <a name="to-view-or-change-available-methods"></a>使用可能なメソッドを表示または変更するには  
  
1.  コンポーネント インターフェイスを開く**プロパティ** ダイアログ ボックス。  
  
     ![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")  
  
2.  をクリックして、**標準メソッド**タブ。  
  
3.  目的のメソッドを選択し、クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [コンポーネント インターフェイスを作成する方法](../core/how-to-create-component-interfaces.md)   
 [付録 C: コンポーネント インターフェイスの使用](../core/appendix-c-using-component-interfaces.md)