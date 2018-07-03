---
title: Analysis Services と BAM プライマリ インポート データベース間の暗号化を有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Analysis Services, enabling encryption
- Primary Import database [BAM], SQL Server Analysis Services
- Primary Import database [BAM], enabling encryption
- SQL Server Analysis Services, Primary Import database [BAM]
ms.assetid: 8107c557-e57c-4569-9ff7-abcb7a8e5243
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aedb10b8818e270164147c4f25d554c42b3d9ee2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005643"
---
# <a name="how-to-enable-encryption-between-analysis-services-and-the-bam-primary-import-database"></a>Analysis Services と BAM プライマリ インポート データベース間の暗号化を有効にする方法
既定では、BAM のインストールまたはアップグレード中、暗号化は無効になっています。 暗号化を有効にするには、BAM 構成 XML ファイルの UseEncryption フラグの値を 1 に設定する必要があります。  
  
 また、SQL Server Analysis Services で暗号化を有効にする必要もあります。 暗号化を有効にする方法の詳細については、次を参照してください。 [Analysis Services インスタンスとクライアントの通信をセキュリティで保護する](http://go.microsoft.com/fwlink/?LinkId=190805)(http://go.microsoft.com/fwlink/?LinkId=190805)します。  
  
### <a name="to-enable-encryption-between-sql-server-analysis-services-and-the-bam-primary-import-database"></a>SQL Server Analysis Services と BAM プライマリ インポート データベース間の暗号化を有効にするには  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] に移動します。  
  
3. 型**bm config の取得のファイル名:\<出力ファイル\>** します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4. **Enter**キーを押します。  
  
5. エクスポートした構成ファイルをテキスト エディターで開き、UseEncryption プロパティ フラグの値を 1 に変更します。  
  
   -   既定の設定:\<プロパティ名 ="UseEncryption"\>0\</Property\>  
  
   -   新しい設定:\<プロパティ名 ="UseEncryption"\>1\</Property\>  
  
6. 」と入力して、BAM 構成を更新**bm 更新プログラム構成ファイル名:\<config ファイル\>** します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)