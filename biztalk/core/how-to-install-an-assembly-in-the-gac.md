---
title: "アセンブリを GAC にインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6afc2f81-fa28-4144-b4bd-21c8f35f2270
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c80e3a5126a56b945b2aa7b53aec71fbe83d678a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-install-an-assembly-in-the-gac"></a>GAC にアセンブリをインストールする方法
手動でインストールしに付属する Gacutil ツールを使用して、グローバル アセンブリ キャッシュ (GAC) 内の BizTalk アセンブリをアンインストール[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。  
  
 使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、BizTalk アセンブリから配置されている場合、GAC に自動的にインストールすることが[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。 BizTalk プロジェクトの展開プロパティでは、このオプションを設定します。参照してください[Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。 このメソッドは、BizTalk 以外の .NET アセンブリを GAC; にインストールを使用することはできませんこのトピックの説明に従って、手動でインストールする必要があります。  
  
> [!NOTE]
>  アセンブリを BizTalk アプリケーションに展開した後も、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用してアセンブリの展開オプションを指定できます。 参照してください[BizTalk アセンブリの展開オプションを変更する方法](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)、および[.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更する方法](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)です。  
  
## <a name="prerequisites"></a>前提条件  
GAC への書き込み権限を持つアカウントでサインインします。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  

  
## <a name="install-using-gacutil"></a>Gacutil を使用したインストールします。
  
1.  ローカル コンピューターに BizTalk アセンブリをコピーします。  
  
2.  開いている**Visual Studio 用開発者コマンド プロンプト**管理者として。  
  
3.  次のように入力します。  
  
     `gacutil /i path_to_assembly_file /f`

    たとえば、次のように入力します。  
    `gacutil /i c:\temp\filename.dll /f`
    
`/f`オプションには、同じアセンブリ名を持つ既存のアセンブリが上書きされます。 Gacutil コマンドおよびオプションの詳細については、次のように入力します。`gacutil /?`です。 

## <a name="uninstall-using-gacutil"></a>Gacutil を使用してアンインストールします。
グローバル アセンブリ キャッシュからアセンブリをアンインストールする (GAC) がアプリケーションを完全に展開解除する必要があります。 このプロセスを自動化することができます。 運用環境にアプリケーションを展開する前に、アプリケーションのアンインストール時に GAC からアセンブリを自動的にアンインストール処理前のスクリプトを記述します。 参照してください[前処理および後処理のスクリプト アプリケーション展開のカスタマイズを使用した](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。  
  
 追加のファイルおよび設定を削除するのにスクリプトを使用することができますも。 参照してください[を他のファイルおよび BizTalk アプリケーションの設定を削除する方法](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)です。  
 
#### <a name="using-the-windows-interface"></a>Windows インターフェイスを使用する場合  
  
1.  Systemdrive%\Windows\Assembly を開きます。  
  
2.  アプリケーションに含まれる各アセンブリ ファイルを右クリックして**アンインストール**、し、**はい**ことを確認します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1.  開いている**Visual Studio 用開発者コマンド プロンプト**管理者として。 
  
2.  次のように入力します。  
  
     `gacutil /u`\<*完全修飾アセンブリ名*\>  
  
     たとえば、次のように入力します。  
     `gacutil /u "hello,Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"`
       
## <a name="see-also"></a>参照  
 [Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
[BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)   
 [BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md)   
 [BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)
 