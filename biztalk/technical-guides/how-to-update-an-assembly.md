---
title: アセンブリを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f456c8f-247a-4d5c-b5af-41e88968779c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68af9966181209b50a4cfb5ee484264d32c60d4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401803"
---
# <a name="how-to-update-an-assembly"></a>アセンブリを更新する方法
このトピックでは、アセンブリと Visual Studio 2010 を使用するアセンブリがデプロイされるアプリケーションのバージョンを更新する方法について説明します。  
  
> [!NOTE]  
>  新しいバージョンのアセンブリを更新する場合は、アプリケーションを再起動する必要はありません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。  
  
## <a name="updating-an-assembly"></a>アセンブリの更新  
  
#### <a name="to-increment-the-version-number-of-an-assembly"></a>アセンブリのバージョン番号をインクリメントするには  
  
1.  ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし をクリックし、**プロパティ**します。  
  
2.  **プロジェクト デザイナー**、クリックして、**アプリケーション**タブ。  
  
3.  右側のウィンドウで次のようにクリックします。**アセンブリ情報**します。  
  
4.  **アセンブリ情報** ダイアログ ボックスで、指定の値、**アセンブリ バージョン**アセンブリのバージョン番号を大きくフィールド。 メジャーまたはマイナー バージョン番号のみを増やす必要があります。 メジャー バージョン番号は、シーケンスの最初の桁 (***n***.0.0.0); マイナー バージョン番号は、シーケンス内の 2 番目の数字 (0 ***。n***.0.0) です。 BizTalk Server では、0.0 などのシーケンスの後のバージョン番号の変更は認識されません。***n***.0 や 0.0.0 ***。n***します。  
  
5.  をクリックして**OK**を閉じる、**アセンブリ情報** ダイアログ ボックス。  
  
6.  プロジェクトを保存します。  
  
    > [!NOTE]  
    >  アセンブリのバージョンを増やすときに、スキーマの競合を回避するために、パイプライン デザイナと BizTalk エクスプローラ オブジェクト モデルを使用します。  
  
#### <a name="to-change-the-application-that-an-assembly-is-deployed-to"></a>アセンブリが展開されているアプリケーションを変更するには  
  
1.  ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし をクリックし、**プロパティ**します。  
  
2.  **プロジェクト デザイナー**、クリックして、**展開**タブ。  
  
3.  右側のウィンドウで アプリケーション名を指定します、**アプリケーション名**フィールド。  
  
4.  いることを確認、**グローバル アセンブリ キャッシュにインストール**プロパティに設定されて**True**します。  
  
    > [!NOTE]  
    >  ソリューションを展開するときに、アセンブリは、新しいアプリケーションに展開され、GAC にインストールされます。