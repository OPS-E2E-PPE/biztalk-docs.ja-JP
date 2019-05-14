---
title: 証明書のエクスポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting certificates
- certificates, exporting
ms.assetid: edeeb300-19d6-44a8-b730-dcd15891cdf9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00fb00a1b256be192ce591b2b11ec70ab9b9d398
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283726"
---
# <a name="exporting-certificates"></a>証明書のエクスポート
このトピックでは、証明書のエクスポート ウィザードを使用して証明書をエクスポートする方法を説明します。 このウィザードを使用すると、パブリック証明書またはプライベート証明書をエクスポートします。  
  
### <a name="to-export-a-partner-certificate"></a>パートナーの証明書をエクスポートするには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2. 展開**証明書 (ローカル コンピューター)**、展開**その他のユーザー**、 をクリックし、**証明書**します。  
  
3. 右側のウィンドウで、証明書の名前を右クリックして**すべてのタスク**、 をクリックし、**エクスポート**します。  
  
4. **証明書のエクスポート ウィザードへようこそ**] ページで [**次**します。  
  
5. **エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。 この形式は、DER encoded binary x.509 バイナリ エンコードされたファイルをエクスポートするまたは Base 64 エンコード ファイルをエクスポートする base-64 でエンコードされた x.509 のいずれかでは、通常します。  
  
   > [!NOTE]
   >  Base-64 で証明書をエンコードするには、UNIX サーバーの証明書を使用することができます。  
  
6. **エクスポートするファイル** ページで **参照**、検索にファイルを保存するには、ファイルの名前を入力、 をクリックして**次へ**、順にクリックします**完了**.  
  
### <a name="to-export-the-home-organization-certificate"></a>ホーム組織証明書をエクスポートするには  
  
1. クリックして**開始**、 をクリックして**実行**、型**runas/user:\<サービスをホスト\>mmc**ここで、 \< *hostservice* \> Microsoft をインストールしたときにホスト サービスに関連するサービスの名前を指定[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]、 をクリックし、 **OK**で Microsoft 管理コンソール (MMC) を実行する、ホスト サービスのコンテキスト。  
  
   > [!NOTE]
   >  実行する、 **runas**コマンドをホーム組織証明書にアクセスするために必要なホスト サービスの id を前提としています。  
  
2. 展開**証明書 - 現在のユーザー**、展開**個人**、 をクリックし、**証明書**します。  
  
3. 右側のウィンドウで、証明書の名前を右クリックして**すべてのタスク**、 をクリックし、**エクスポート**します。  
  
4. **証明書のエクスポート ウィザードへようこそ**] ページで [**次**します。  
  
5. 証明書の秘密キーに関連付けられている公開キーをエクスポートするのままに**秘密キーをエクスポートしません**選択します。 秘密キーをエクスポートするには、次のように選択します。**はい、秘密キーをエクスポート**します。  
  
   > [!NOTE]
   >  選択した場合**はい、秘密キーをエクスポート**パートナーには、生成されたファイルを送信しないことを強くお勧めします。  
  
   > [!NOTE]
   >  **はい、秘密キーをエクスポート**されませんを行った場合、秘密キー エクスポート可能な最初にインポートしたときにオプションを実行できなくなります。  
  
6. **エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。 この形式は、DER encoded binary x.509 バイナリ エンコードされたファイルをエクスポートするまたは Base 64 エンコード ファイルをエクスポートする base-64 でエンコードされた x.509 のいずれかでは、通常します。  
  
   > [!NOTE]
   >  Base-64 で証明書をエンコードするには、UNIX サーバーの証明書を使用することができます。  
  
7. **エクスポートするファイル** ページで **参照**、検索にファイルを保存するには、ファイルの名前を入力、 をクリックして**次へ**、順にクリックします**完了**.  
  
## <a name="see-also"></a>参照  
 [証明書の管理](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)