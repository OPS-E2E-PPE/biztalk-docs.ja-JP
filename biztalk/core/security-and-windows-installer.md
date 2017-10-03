---
title: "セキュリティと Windows インストーラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, Windows installer
- Windows installer
ms.assetid: efa68c3e-2006-4665-bd41-07defaf4e2e2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4418994a4b5ff705d1faef751ac8c96ba86f9dc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-and-windows-installer"></a>セキュリティと Windows インストーラー
Windows インストーラーは、BizTalk アプリケーションをインストールおよび更新するための強力なツールです。 Windows インストーラーを使用する場合は、悪意を持って作成された Windows インストーラー (.msi) ファイルがもたらす可能性のあるセキュリティ上の問題に注意し、これを回避するための適切な措置をとる必要があります。  
  
 一般に、.msi ファイルを実行するのは管理者であるため、アプリケーションのインストールまたは更新時に実行するプロセスには高度な権限が与えられています。 悪意のある .msi ファイル作成者によって、このことが次のように悪用されないとも限りません。  
  
-   システムまたはファイルに望ましくない変更を加えるスクリプト ファイルを実行する。  
  
-   COM カタログを上書きする。  
  
-   レジストリ値を上書きする。 このような変更はロールバックできません。  
  
-   ファイル システムを飽和状態にする。  
  
 .msi ファイルを使用する際は、少なくとも次の点に注意してください。  
  
-   全面的に信頼できる .msi ファイルのみをインストールします。  
  
    > [!NOTE]
    >  ベスト プラクティスとして、.msi ファイルの作成担当者は、ファイルのソースが信頼できることをユーザーが確認できるように .msi ファイルに署名する追加手順を実行することをお勧めします。  
  
-   .msi ファイルを実稼働環境で使用する前に十分にテストします。  
  
-   .msi ファイルは、適切な随意アクセス制御リスト (DACL) によってセキュリティで保護される保護フォルダーに格納します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開のセキュリティに関する考慮事項](../core/security-considerations-for-application-deployment.md)