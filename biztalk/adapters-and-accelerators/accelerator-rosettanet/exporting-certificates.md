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
ms.openlocfilehash: 5f5a4390cc62fdb46cbad9993a106d98163c0838
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975867"
---
# <a name="exporting-certificates"></a>証明書のエクスポート
ここでは、証明書のエクスポート ウィザードを使用して証明書をエクスポートする方法について説明します。 このウィザードを使用すると、パブリック証明書またはプライベート証明書のいずれかをエクスポートできます。  
  
### <a name="to-export-a-partner-certificate"></a>パートナー証明書をエクスポートするには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2. 展開**証明書 (ローカル コンピューター)**、展開**その他のユーザー**、 をクリックし、**証明書**します。  
  
3. 右側のウィンドウで、証明書の名前を右クリックして**すべてのタスク**、 をクリックし、**エクスポート**します。  
  
4. **証明書のエクスポート ウィザードへようこそ**] ページで [**次**します。  
  
5. **エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。 この形式は、通常、バイナリ エンコード ファイルをエクスポートする DER encoded binary x.509 か、Base-64 エンコード ファイルをエクスポートする Base-64 encoded x.509 のいずれかです。  
  
   > [!NOTE]
   >  Base-64 で証明書をエンコードすると、その証明書を UNIX サーバーで使用できます。  
  
6. **エクスポートするファイル** ページで **参照**、検索にファイルを保存するには、ファイルの名前を入力、 をクリックして**次へ**、順にクリックします**完了**.  
  
### <a name="to-export-the-home-organization-certificate"></a>ホーム組織証明書をエクスポートするには  
  
1. クリックして**開始**、 をクリックして**実行**、型**runas/user:\<サービスをホスト\>mmc**ここで、 \< *hostservice* \> Microsoft をインストールしたときにホスト サービスに関連するサービスの名前を指定[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]、] をクリックし、 **OK**で Microsoft 管理コンソール (MMC) を実行する、ホスト サービスのコンテキスト。  
  
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
  
6. **エクスポート ファイルの形式** ページで、ファイルを使用する形式を選択します。 この形式は、通常、バイナリ エンコード ファイルをエクスポートする DER encoded binary x.509 か、Base-64 エンコード ファイルをエクスポートする Base-64 encoded x.509 のいずれかです。  
  
   > [!NOTE]
   >  Base-64 で証明書をエンコードすると、その証明書を UNIX サーバーで使用できます。  
  
7. **エクスポートするファイル** ページで **参照**、検索にファイルを保存するには、ファイルの名前を入力、 をクリックして**次へ**、順にクリックします**完了**.  
  
## <a name="see-also"></a>参照  
 [証明書の管理](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)