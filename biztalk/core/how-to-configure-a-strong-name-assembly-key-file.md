---
title: "厳密な名前のアセンブリ キー ファイルを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5778a8ec-f5f7-4ae1-a57e-99f6503f044c
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e77f72effa1a9c9193f9ce589ebe22b65feb5a85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリ キー ファイルを構成する方法
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] では、BizTalk ソリューションを展開するプロセスで、まずアセンブリのビルドが行われます。 このとき各アセンブリは、厳密に署名されている必要があります。 厳密な名前のアセンブリ キー ファイルとプロジェクトを関連付けることによって、アセンブリを厳密署名できます。 まだ行っていない場合は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からソリューションを展開する前に、次の手順に従って、厳密な名前のアセンブリ キー ファイルを生成し、ソリューション内の各プロジェクトに割り当ててください。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますログインする必要がのメンバーであるアカウントを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者のグループです。 また、使用するアカウントには、グローバル アセンブリ キャッシュ (GAC) に対する書き込みアクセス許可が必要です。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  
  
### <a name="to-configure-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリ キー ファイルを構成するには  
  
1.  開始**Visual Studio コマンド プロンプト**です。  
  
2.  コマンド プロンプトで、キー ファイルを格納するフォルダーから次のコマンドを入力し、Enter キーを押します。  
  
     **sn/k***file_name* **.snk**   
  
     例: **sn/k ErrorHandling.snk**  
  
     確認メッセージを**キーのペアに書き込まれる** \< *file_name*>**.snk** `,`コマンド ラインで表示されます。  
  
3.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、プロジェクトを右クリックし、をクリックして**プロパティ**です。  
  
4.  をクリックして、**署名**タブを選び**参照**で、**厳密な名前キー ファイルを選択して**ボックスの一覧です。  
  
5.  キー ファイルを参照してクリックします。 をクリックして**開く**、プロジェクトのプロパティを閉じます。  
  
6.  この厳密な名前のアセンブリ キー ファイルを使用して展開するソリューション内のプロジェクトごとに、手順 3. ～ 6. を繰り返します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開します。](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)