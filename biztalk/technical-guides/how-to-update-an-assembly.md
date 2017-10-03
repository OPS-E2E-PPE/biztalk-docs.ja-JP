---
title: "アセンブリを更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f456c8f-247a-4d5c-b5af-41e88968779c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 163b06706652b1f65b9a76e3feea8911a2ca4c88
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-an-assembly"></a>アセンブリを更新する方法
このトピックでは、アセンブリと Visual Studio 2010 を使用するアセンブリがデプロイされるアプリケーションのバージョンを更新する方法について説明します。  
  
> [!NOTE]  
>  アセンブリを新しいバージョンで更新する場合は、アプリケーションを再起動する必要はありません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。  
  
## <a name="updating-an-assembly"></a>アセンブリの更新  
  
#### <a name="to-increment-the-version-number-of-an-assembly"></a>アセンブリのバージョン番号をインクリメントするには  
  
1.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを右クリックし、をクリックして**プロパティ**です。  
  
2.  **プロジェクト デザイナー**をクリックして、**アプリケーション**タブです。  
  
3.  右側のウィンドウでをクリックして**アセンブリ情報**です。  
  
4.  **アセンブリ情報** ダイアログ ボックスで、値を指定、**アセンブリ バージョン**をアセンブリのバージョン番号を増やすにはフィールドです。 メジャー バージョン番号またはマイナー バージョン番号だけを増分してください。 メジャー バージョン番号は、シーケンスの最初の桁 (***n***.0.0.0); マイナー バージョン番号は、シーケンス内の 2 番目の数字 (0*** 。n ***.0.0) です。 BizTalk Server では、0.0 などのシーケンスの後のバージョン番号の変更は認識されません。*** n ***.0 や 0.0.0 と表示されます***。n***.  
  
5.  をクリックして**OK**を閉じる、**アセンブリ情報** ダイアログ ボックス。  
  
6.  プロジェクトを保存します。  
  
    > [!NOTE]  
    >  パイプライン デザイナーおよび BizTalk エクスプローラー オブジェクト モデルを使用して、アセンブリ バージョンを増やす際のスキーマの競合を避けます。  
  
#### <a name="to-change-the-application-that-an-assembly-is-deployed-to"></a>アセンブリが展開されているアプリケーションを変更するには  
  
1.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを右クリックし、をクリックして**プロパティ**です。  
  
2.  **プロジェクト デザイナー**をクリックして、**展開**タブです。  
  
3.  右側のウィンドウで、アプリケーション名を指定で、**アプリケーション名**フィールドです。  
  
4.  いることを確認、**グローバル アセンブリ キャッシュにインストール**プロパティに設定されている**True**です。  
  
    > [!NOTE]  
    >  ソリューションを展開するときに、アセンブリは、新しいアプリケーションに展開され、GAC にインストールされます。