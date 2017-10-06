---
title: "証明書のエクスポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exporting certificates
- certificates, exporting
ms.assetid: edeeb300-19d6-44a8-b730-dcd15891cdf9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1898162b27956e4e527013ff765edf6aea440e9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exporting-certificates"></a>証明書のエクスポート
ここでは、証明書のエクスポート ウィザードを使用して証明書をエクスポートする方法について説明します。 このウィザードを使用すると、パブリック証明書またはプライベート証明書のいずれかをエクスポートできます。  
  
### <a name="to-export-a-partner-certificate"></a>パートナー証明書をエクスポートするには  
  
1.  をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] をクリックし、 [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **管理コンソール**.  
  
2.  展開**証明書 (ローカル コンピューター)**、展開**ほかの人**、クリックして**証明書**です。  
  
3.  右側のウィンドウで、証明書の名前を右クリックし、**すべてのタスク**、クリックして**エクスポート**です。  
  
4.  **証明書のエクスポート ウィザードへようこそ** ページで、をクリックして**次**です。  
  
5.  **エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。 この形式は、通常、バイナリ エンコード ファイルをエクスポートする DER encoded binary x.509 か、Base-64 エンコード ファイルをエクスポートする Base-64 encoded x.509 のいずれかです。  
  
    > [!NOTE]
    >  Base-64 で証明書をエンコードすると、その証明書を UNIX サーバーで使用できます。  
  
6.  **エクスポートするファイル** ページで、をクリックして**参照**、検索、ファイルの名前を入力ファイルを保存する場所をクリックして**次へ**、順にクリック**完了**.  
  
### <a name="to-export-the-home-organization-certificate"></a>ホーム組織証明書をエクスポートするには  
  
1.  をクリックして**開始**をクリックして**実行**、型**runas/user:\<サービスをホスト > mmc**ここで、 \< *hostservice*> をインストールしたときに、ホスト サービスに関連付けられたサービスの名前を指定[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]、順にクリック**OK**を実行する、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]のコンテキストで管理コンソール (MMC)、ホスト サービス。  
  
    > [!NOTE]
    >  実行する、 **runas**コマンドをホーム組織証明書にアクセスに必要なホスト サービスの id を前提としています。  
  
2.  展開**証明書 - 現在のユーザー**、展開**個人**、クリックして**証明書**です。  
  
3.  右側のウィンドウで、証明書の名前を右クリックし、**すべてのタスク**、クリックして**エクスポート**です。  
  
4.  **証明書のエクスポート ウィザードへようこそ** ページで、をクリックして**次**です。  
  
5.  証明書の秘密キーに関連付けられている公開キーをエクスポートするのままにして**いいえ、秘密キーをエクスポートしません**選択します。 秘密キーをエクスポートするには選択**はい、秘密キーをエクスポート**です。  
  
    > [!NOTE]
    >  選択した場合**はい、秘密キーをエクスポート**パートナーに、生成されたファイルを送信しないことを強くお勧めします。  
  
    > [!NOTE]
    >  **はい、秘密キーをエクスポート**されませんを行った場合、秘密キー エクスポート可能な最初にインポートしたときにオプションを実行できなくなります。  
  
6.  **エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。 この形式は、通常、バイナリ エンコード ファイルをエクスポートする DER encoded binary x.509 か、Base-64 エンコード ファイルをエクスポートする Base-64 encoded x.509 のいずれかです。  
  
    > [!NOTE]
    >  Base-64 で証明書をエンコードすると、その証明書を UNIX サーバーで使用できます。  
  
7.  **エクスポートするファイル** ページで、をクリックして**参照**、検索、ファイルの名前を入力ファイルを保存する場所をクリックして**次へ**、順にクリック**完了**.  
  
## <a name="see-also"></a>参照  
 [証明書の管理](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)