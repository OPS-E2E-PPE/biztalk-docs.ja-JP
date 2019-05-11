---
title: インターフェイスをセキュリティで保護されたコンポーネントを支援する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, helping to secure
- security, component interfaces
ms.assetid: 03b2af44-78e7-4fdc-bfa3-7697b2a60986
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca6e0dcbd265dbfcdc6f128f2ff7b58e301f2e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385027"
---
# <a name="how-to-help-secure-component-interfaces"></a>コンポーネント インターフェイスをセキュリティ保護する方法
コンポーネント インターフェイスのテストを開始する前に、そのセキュリティを設定する必要があります。 次の手順は、PeopleSoft バージョン 8.4 のコンポーネント インターフェイスのセキュリティを構成する方法をについて説明しますが、バージョン 8.1 の手順を使用することができます。  
  
### <a name="to-configure-interface-security"></a>インターフェイスのセキュリティを構成するには  
  
1.  展開**PeopleTools**、展開**セキュリティ**、展開**ユーザー プロファイル**、順に展開**アクセス許可とロール**します。  
  
     ![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")  
  
2.  クリックして**アクセス許可の一覧**します。  
  
3.  **[検索]** をクリックします。  
  
     ![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")  
  
4.  **Permission Lists Search**ウィンドウで、関連するアクセス許可の一覧を選択します。  
  
     次のウィンドウが表示されます。  
  
     ![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")  
  
5.  右矢印をクリックして、 **sign-on Times**タブを複数のタブが表示されます。  
  
     ![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")  
  
6.  をクリックして、**コンポーネント インターフェイス**タブ。  
  
7.  をクリックして、+ (プラス) 記号を新しい行を追加、**コンポーネント インターフェイス**一覧。  
  
     コンポーネント インターフェイスの名前を入力できるフィールドが表示されます。  
  
     ![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")  
  
8.  コンポーネント インターフェイスの名前を入力し、クリックして**編集**します。  
  
     この例では、AR_ITEM_AGENT のコンポーネント インターフェイスを使用します。  
  
     ![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")  
  
9. 一覧で、各メソッドでは、必要なアクセス レベルを選択し、 **OK**します。  
  
     次のウィンドウが表示されます。  
  
     ![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")  
  
10. 右側のウィンドウで下にスクロールし、をクリックして**保存**します。  
  
## <a name="see-also"></a>参照  
 [付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)   
 [付録 c:コンポーネント インターフェイスの使用](../core/appendix-c-using-component-interfaces.md)