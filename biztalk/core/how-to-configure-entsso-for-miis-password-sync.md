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
ms.openlocfilehash: 9aed37b5b3883242005f46dcc6a0253a4971d680
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005227"
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a>MIIS パスワード同期用に ENTSSO を構成する方法
XML ファイルと Microsoft Identity Integration Server (MIIS) の構成が終わったら、残りの構成手順は、エンタープライズ シングル サインオン (ENTSSO) システムで行います。  
  
### <a name="to-allow-password-sync-from-miis"></a>MIIS からパスワード同期を有効にするには  
  
1.  エンタープライズ シングル サインオン、クリックして、**サーバー**ノード。  
  
2.  適切なサーバーを右クリックし、をクリックして**プロパティ**します。  
  
3.  をクリックして、**パスワード同期**タブ。  
  
4.  選択**MIIS からパスワード同期を許可する**します。  
  
5.  **[OK]** をクリックします。  
  
### <a name="to-enable-password-sync-on-the-system-level"></a>パスワード同期をシステム レベルで有効にするには  
  
1. エンタープライズ シングル サインオンを右クリックし、**システム**ノード。  
  
2. **[プロパティ]** をクリックします。  
  
    **プロパティ** ダイアログ ボックスが表示されます。  
  
3. をクリックして、**オプション**タブ。  
  
4. **パスワード同期を有効にする**フィールドで、**アダプターから Windows**します。  
  
    **追加の構成**  
  
    最後に、次のいずれかを構成する必要があります。  
  
   - Windows パスワード同期を受け入れるパスワード同期アダプタ  
  
   - 少なくとも 1 つのアプリケーションに対して有効になっている直接パスワード同期  
  
     構成方法については、パスワード同期のドキュメントを参照してください。  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a>MIIS パスワード同期用に EntSSO MA を構成するには  
  
1.  ENTSSO 管理エージェントで**プロパティ**] ページで [**拡張機能の構成**します。  
  
2.  **パスワード拡張機能の接続情報**フィールドに、をクリックして**設定**します。  
  
3.  **接続先**フィールド、パスワードの変更を受信するコンピュータの名前を入力します。  
  
     このコンピュータ名は、ドメインの ENTSSO サービスに対するサービス プリンシパル名 (SPN) を作成したときと同じ形式にする必要があります。  
  
     以下に例を示します。  
  
     短い形式の SPN である ENTSSO/ABCD1411 を作成した場合は、「ABCD1411」と入力します。  
  
4.  長い形式の SPN である ENTSSO/ABCD1411.CompanyName.com を作成した場合は、「ABCD1411.CompanyName.com」と入力します。  
  
### <a name="additional-configuration-steps"></a>追加の構成手順  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Identity Integration Server**、順にクリックします**Identity Manager**します。  
  
2.  **[ツール]** メニューの **[オプション]** をクリックします。  
  
3.  選択**パスワード同期を有効にする**します。  
  
4.  **管理エージェントを表示**、 **ADMA**します。  
  
5.  **アクション**ペインで、**プロパティ**します。  
  
6.  **プロパティ** ページで、**ディレクトリ パーティションの構成**、し、**パスワードの同期ソースとしてこのパーティションを有効にする**します。  
  
7.  クリックして**ターゲット**、し、ENTSSOMA2 が MIIS からパスワード変更を受信できるようにします。 [ENTSSOMA] の選択を解除します。 をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
8.  **管理エージェント**ビューで、 **ENTSSOMA2**します。 右側のウィンドウで次のように選択します。**プロパティ**します。 **プロパティ**] ページで [**拡張機能の構成**します。  
  
9. 確認します**パスワード管理を有効にする**が選択されているし、をクリックし、**設定**します。  
  
10. **接続設定**ダイアログ ボックスで、次を指定します。  
  
    -   接続: INTSVR1.fabrikam.com  
  
    -   ユーザー: fabrikam\ssosvcact  
  
    -   パスワード: ssosvcact  
  
        > [!NOTE]
        >  このアカウントは、INTSVR1.fabrikam.com に対して構成されている ENTSSO サービス アカウントと一致させる必要があります。  
  
11. をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
12. MIIS のパスワード同期を無効にすることもできます。 これを実行する**Identity Manager**、クリックして、**ツール** メニューのをクリックして**オプション**、選択を解除**パスワード同期を有効にする**します。  
  
     次の制限が適用されます。  
  
    -   パスワード同期を正しく機能させるには、ENTSSO 管理エージェントが通信する ENTSSO サービス アカウントに対して SPN を構成する必要があります。  
  
    -   MIIS と ENTSSO サーバー間の通信には Kerberos が必要です。  
  
13. ENTSSO 管理エージェントの MIIS 接続構成でパスワード拡張機能を構成する場合は、指定したアカウントが、MIIS からパスワードを受信する ENTSSO サーバーのサービス アカウントと一致する必要があります。  
  
## <a name="see-also"></a>参照  
 [ENTSSO 管理エージェントを使用する方法](../core/how-to-use-the-entsso-management-agent.md)