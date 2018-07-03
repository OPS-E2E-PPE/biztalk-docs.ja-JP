---
title: Oracle E-business Suite のトランザクションを許可する MS 分散トランザクション コーディネーターを有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 634538e5-7292-4b3f-85b0-c6db86d0dbd2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53037e9a7dc1ccc3c0ef21860696060ad1c046a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984995"
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a>Oracle E-business Suite のトランザクションを許可する MS 分散トランザクション コーディネーターを有効にします。
使用するアプリケーションの作成を開始する前に、MSDTC を構成、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
Oracle E-business Suite を使用して、操作を実行、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (を通じて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデル、または WCF チャネル モデル)、トランザクション スコープ内で実行することができます。 クライアント プログラムは、1 つ以上のトランザクション リソースを同じトランザクションの一部としては場合、トランザクションは MSDTC トランザクションに昇格を取得します。 MSDTC トランザクションのスコープ内での操作を実行するアダプターを有効にするには、実行しているコンピューターで MSDTC を構成、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、Oracle E-business suite とします。 また、追加 MSDTC ファイアウォールで、例外の一覧に、組み込みの Windows ファイアウォールがあります。 
  
> [!NOTE]
>  MSDTC を構成する手順は、さまざまなオペレーティング システムによって異なります。 このトピックに記載の手順は、Windows クライアントおよび Windows Server オペレーティング システムに適用されます。  
  
## <a name="configure-msdtc"></a>MSDTC を構成します。  
  
1. 開いている**コンポーネント サービス**します。  

   または、**サーバー マネージャー**、**ツール**、し、**コンポーネント サービス**。  
  
2. 展開**コンポーネント サービス**、展開**コンピューター**、展開**マイ コンピューター**、展開**分散トランザクション コーディネーター**、右クリック**ローカル DTC**、選び**プロパティ**します。  
  
3. **[セキュリティ]** タブをクリックします。このタブでは、次のすべてを選択します。 

   - **ネットワーク DTC アクセス**
   - **リモート クライアントを許可します。** 
   - **受信を許可する** 
   - **送信を許可する** 
   - **必要ない Authetnication**
  
4. **[OK]** を選択して変更を保存します。  
  
5. MSDTC サービスを再起動するメッセージが表示されたら、選択**はい**します。 MSDTC サービスが再起動した後は、プロパティとコンポーネント サービス MMC を閉じます。 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>MSDTC を Windows ファイアウォールの例外リストに追加します。  

> [!TIP] 
>  Microsoft 分散 Tansaction コーディネーター (MSDTC) は、ファイアウォールで既に許可場合があります。 そうである場合は、受信の規則として表示されます。 表示されない場合は、このセクションを使用して、MSDTC を許可します。 

1.  開いている**Windows ファイアウォール**を選択し、**詳細設定**左側にします。  

    または、**サーバー マネージャー**、**ツール**、し、**セキュリティが強化された Windows ファイアウォール**。  
  
2.  右クリックして**受信の規則**、選択および**新しいルール**します。  
  
3.  ウィザード。 

    1. 選択**プログラム**を選択し、**次**します。 
    2. 設定、**プログラムのパス**に`%SystemRoot%\system32\msdtc.exe`を選択し、**次**します。  
    3. **接続を許可する**、選び**次**します。
    4. 選択**ドメイン**を選択し、**次**します。
    5. などの任意の名前を入力します`MSDTC for Oracle EBS`、選び**完了**します。
  
5.  ウィザードを完了し、Windows ファイアウォールを閉じます。 
  
## <a name="next"></a>Next 
[Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)