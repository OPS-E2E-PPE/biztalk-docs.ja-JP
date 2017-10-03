---
title: "Oracle E-business Suite のトランザクションを許可する MS 分散トランザクション コーディネーターを有効にする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 634538e5-7292-4b3f-85b0-c6db86d0dbd2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0597c050e1531d71a62af04fe6c825653076297c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a>Oracle E-business Suite のトランザクションを許可する MS 分散トランザクション コーディネーターを有効にします。
使用するアプリケーションの作成を開始する前に、MSDTC を構成、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
Oracle E-business Suite を使用して、操作を実行、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (を通じて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデルで、または WCF チャネル モデル)、トランザクション スコープ内で実行することができます。 場合は、クライアント プログラムは、同じトランザクションの一部として 1 つ以上のトランザクション リソースを持つ、トランザクションが MSDTC トランザクションに昇格を取得します。 MSDTC トランザクションのスコープ内で操作を実行するアダプターを有効にするを実行しているコンピューターで MSDTC を構成、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、および Oracle E-business Suite でします。 また、追加 MSDTC、ファイアウォールの例外の一覧に、組み込みの Windows ファイアウォールがあります。 
  
> [!NOTE]
>  MSDTC を構成する手順は、さまざまなオペレーティング システムによって異なります。 このトピックに記載された手順は、Windows クライアントおよび Windows Server オペレーティング システムに適用されます。  
  
## <a name="configure-msdtc"></a>MSDTC を構成します。  
  
1.  開いている**コンポーネント サービス**です。  

    または、**サーバー マネージャー****ツール**、し、**コンポーネント サービス**です。  
  
2.  展開**コンポーネント サービス**、展開**コンピューター**、展開**マイ コンピューター**、展開**分散トランザクション コーディネーター**、右クリック**ローカル DTC**を選択して**プロパティ**です。  
  
3.  **[セキュリティ]** タブをクリックします。このタブでは、次のすべてを選択します。 

  - **ネットワーク DTC アクセス**
  - **リモート クライアントを許可します。** 
  - **受信を許可する** 
  - **送信を許可する** 
  - **必要ない Authetnication**
  
4.  **[OK]** を選択して変更を保存します。  
  
5.  MSDTC サービスを再起動するのには、メッセージが表示されたら、選択**はい**です。 MSDTC サービスを再起動した後は、プロパティとコンポーネント サービス MMC を閉じます。 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>MSDTC を Windows ファイアウォールの例外リストに追加します。  

> [!TIP] 
>  Microsoft 分散 Tansaction コーディネーター (MSDTC) は、ファイアウォールで既にできる場合があります。 その場合は、受信の規則として表示されます。 表示されない場合は、このセクションを使用して、MSDTC を許可します。 

1.  開いている**Windows ファイアウォール**を選択し、**詳細設定**左側です。  

    または、**サーバー マネージャー****ツール**、し、**セキュリティが強化された Windows ファイアウォール**です。  
  
2.  右クリックして**受信の規則**を選択して**新しいルール**です。  
  
3.  ウィザード。 

    1. 選択**プログラム**を選択して**次**です。 
    2. 設定、**プログラムのパス**に`%SystemRoot%\system32\msdtc.exe`を選択し、**次**です。  
    3. **接続を許可する**を選択して**次**です。
    4. 選択**ドメイン**を選択して**次**です。
    5. など、任意の名前を入力`MSDTC for Oracle EBS`を選択して**完了**です。
  
5.  ウィザードを完了し、Windows ファイアウォールを閉じます。 
  
## <a name="next"></a>Next 
[Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)