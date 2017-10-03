---
title: "インターフェイスをセキュリティで保護されたコンポーネントを保護する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, helping to secure
- security, component interfaces
ms.assetid: 03b2af44-78e7-4fdc-bfa3-7697b2a60986
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54136aaeae9578ae4e438c5bd8b95b902d618f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-help-secure-component-interfaces"></a>コンポーネント インターフェイスをセキュリティで保護する方法
コンポーネント インターフェイスのテストを開始する前に、セキュリティを設定する必要があります。 次の手順では、PeopleSoft バージョン 8.4 のコンポーネント インターフェイスのセキュリティを構成する方法について説明しますが、この手順はバージョン 8.1 にも使用できます。  
  
### <a name="to-configure-interface-security"></a>インターフェイスのセキュリティを構成するには  
  
1.  展開**PeopleTools**、展開**セキュリティ**、展開**ユーザー プロファイル**、順に展開**アクセス許可とロール**です。  
  
     ![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")  
  
2.  をクリックして**アクセス許可の一覧**です。  
  
3.  **[検索]**をクリックします。  
  
     ![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")  
  
4.  **Permission Lists Search**  ウィンドウで、関連するアクセス許可リストを選択します。  
  
     次のようなウィンドウが表示されます。  
  
     ![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")  
  
5.  次に、右矢印をクリックして、 **sign-on Times**他のタブを表示するタブです。  
  
     ![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")  
  
6.  クリックして、**コンポーネント インターフェイス**タブです。  
  
7.  クリックして、+ (に新しい行を追加する記号 +)、**コンポーネント インターフェイス** ボックスの一覧です。  
  
     コンポーネント インターフェイス名を入力できるフィールドが表示されます。  
  
     ![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")  
  
8.  コンポーネント インターフェイスの名前を入力して、クリックして**編集**です。  
  
     この例では、AR_ITEM_AGENT というコンポーネント インターフェイスを使用しています。  
  
     ![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")  
  
9. 一覧で、各メソッドで必要なアクセス レベルを選択し、をクリックして**OK**です。  
  
     次のようなウィンドウが表示されます。  
  
     ![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")  
  
10. 右側のペインで下にスクロールし、をクリックして**保存**です。  
  
## <a name="see-also"></a>参照  
 [付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)   
 [付録 c: コンポーネント インターフェイスの使用](../core/appendix-c-using-component-interfaces.md)