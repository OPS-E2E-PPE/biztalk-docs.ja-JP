---
title: MIIS パスワード同期用に ENTSSO を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89438935-37c1-4ac9-9ca2-7af8d9bfd3ae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9716e855a6eea34a7f24c534dabd57c8a628c960
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386320"
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a>MIIS パスワード同期用に ENTSSO を構成する方法
XML ファイルと Microsoft Identity Integration Server (MIIS) を構成した後、残りの構成手順は、エンタープライズ シングル サインオン (ENTSSO) システムで行います。  
  
### <a name="to-allow-password-sync-from-miis"></a>MIIS からパスワード同期を許可するには  
  
1.  エンタープライズ シングル サインオン、クリックして、**サーバー**ノード。  
  
2.  適切なサーバーを右クリックし、をクリックして**プロパティ**します。  
  
3.  をクリックして、**パスワード同期**タブ。  
  
4.  選択**MIIS からパスワード同期を許可する**します。  
  
5.  **[OK]** をクリックします。  
  
### <a name="to-enable-password-sync-on-the-system-level"></a>システム レベルでのパスワード同期を有効にするには  
  
1. エンタープライズ シングル サインオンを右クリックし、**システム**ノード。  
  
2. **[プロパティ]** をクリックします。  
  
    **プロパティ** ダイアログ ボックスが表示されます。  
  
3. をクリックして、**オプション**タブ。  
  
4. **パスワード同期を有効にする**フィールドで、**アダプターから Windows**します。  
  
    **追加の構成**  
  
    最後に、次のいずれかを構成する必要があります。  
  
   - Windows パスワード同期を受け入れるパスワード同期アダプター。  
  
   - 直接パスワード同期を少なくとも 1 つのアプリケーションで有効にします。  
  
     これを行う方法については、パスワード同期は、マニュアルを参照してください。  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a>MIIS パスワード同期用に EntSSO MA を構成するには  
  
1.  ENTSSO 管理エージェントで**プロパティ**] ページで [**拡張機能の構成**します。  
  
2.  **パスワード拡張機能の接続情報**フィールドに、をクリックして**設定**します。  
  
3.  **接続先**フィールド、パスワードの変更を受信するコンピュータの名前を入力します。  
  
     コンピューター名は、ドメインの ENTSSO サービスのサービス プリンシパル名 (SPN) を作成するときに使用されたのと同じ形式である必要があります。  
  
     例 :  
  
     短い形式の SPN ENTSSO/ABCD1411 を = し、ABCD1411 を入力します。  
  
4.  長い形式の SPN ENTSSO/ABCD1411.CompanyName.com を = し、ABCD1411.CompanyName.com を入力します。  
  
### <a name="additional-configuration-steps"></a>追加の構成手順  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Identity Integration Server**、順にクリックします**Identity Manager**します。  
  
2.  **[ツール]** メニューの **[オプション]** をクリックします。  
  
3.  選択**パスワード同期を有効にする**します。  
  
4.  **管理エージェントを表示**、 **ADMA**します。  
  
5.  **アクション**ペインで、**プロパティ**します。  
  
6.  **プロパティ** ページで、**ディレクトリ パーティションの構成**、し、**パスワードの同期ソースとしてこのパーティションを有効にする**します。  
  
7.  クリックして**ターゲット**、し、ENTSSOMA2 が MIIS からパスワード変更を受信できるようにします。 ENTSSOMA の選択を解除します。 をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
8.  **管理エージェント**ビューで、 **ENTSSOMA2**します。 右側のウィンドウで次のように選択します。**プロパティ**します。 **プロパティ**] ページで [**拡張機能の構成**します。  
  
9. 確認します**パスワード管理を有効にする**が選択されているし、をクリックし、**設定**します。  
  
10. **接続設定**ダイアログ ボックスで、次を指定します。  
  
    -   接続します。INTSVR1.fabrikam.com  
  
    -   ユーザー: fabrikam\ssosvcact  
  
    -   パスワード: ssosvcact  
  
        > [!NOTE]
        >  このアカウントは、INTSVR1.fabrikam.com に対して構成されている ENTSSO サービス アカウントと一致する必要があります。  
  
11. をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
12. MIIS のパスワード同期を無効にすることができます。 これを実行する**Identity Manager**、クリックして、**ツール** メニューのをクリックして**オプション**、選択を解除**パスワード同期を有効にする**します。  
  
     次の制限が適用されます。  
  
    -   パスワード同期が正常に機能する、ENTSSO 管理エージェントと通信する ENTSSO サービス アカウントの SPN を構成する必要があります。  
  
    -   MIIS と ENTSSO サーバー間の通信には、Kerberos が必要です。  
  
13. ENTSSO 管理エージェントの MIIS 接続構成でパスワード拡張機能を構成するときに、指定されたアカウントは、MIIS からパスワードを受信する ENTSSO サーバーのサービス アカウントと一致する必要があります。  
  
## <a name="see-also"></a>参照  
 [ENTSSO 管理エージェントを使用する方法](../core/how-to-use-the-entsso-management-agent.md)