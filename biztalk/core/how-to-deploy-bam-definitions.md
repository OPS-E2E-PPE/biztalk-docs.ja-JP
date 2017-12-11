---
title: "BAM 定義を展開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, definitions [BAM]
- managing [BAM definitions], deploying definitions
- definitions [BAM], deploying
- Deploy-All command [BAM]
ms.assetid: 02b8888c-6f6c-45dd-8445-6e507a02f5f0
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094a37d90db41e505adeaec3a31ece9128785e04
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-bam-definitions"></a>BAM 定義を展開する方法
管理者を使用して、**展開すべて**Excel ブックまたは XML 定義ファイルから BAM 定義を展開する BAM 管理ユーティリティのコマンドは、ブックからエクスポートします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の完全インストールを実行すると、構成ウィザードで BAM 構成 XML が自動的に構成されます。  
  
> [!NOTE]
>  複数のユーザーは、Excel 用 BAM アドインで作業は場合、は、同じバージョンの Microsoft Data Access Components (MDAC) があることをお勧めします。 同じバージョンを使用しないと、互換性の問題が発生する場合があります。 具体的には、新しいバージョンの MDAC を使用しているコンピューター上でテンプレートを作成した後、古いバージョンの MDAC を使用しているコンピューターでそのテンプレートを開くと、コンパイラ エラーが発生します。  
  
> [!NOTE]
>  各データ ディメンション (例、Location) では、データ項目 (例、City) を 1 つだけ使用できます。 City を Region など別のデータ ディメンションで再度使用することはできません。  
  
> [!IMPORTANT]
>  BAM Excel ブック (.xls) のセキュリティを確認してから展開することをお勧めします。 BAM Excel ブックのセキュリティを確認するには、管理用コンピューターで Excel を使用します。 ブックを展開する前に開き、マクロのセキュリティが [高] に設定されているし、警告がないことを確認します。  
  
> [!IMPORTANT]
>  BAM データベースで、"bam _\<.\>"SQL のすべてのエンティティの名前付け規則は予約されています (テーブル、インデックス、ストアド プロシージャ、ロールなど.) です。*そうしない*この名前付け規則を使用して、SQL エンティティを作成する以外の場合は、このような使用法は動作が不安定になる可能性があります。  
  
 BAM 定義 XML ファイルを展開する前に、このファイルの作成に使用したロケールが展開先のコンピューターのロケールに一致することを確認する必要があります。 たとえば、日本語版の Microsoft Windows を実行しているコンピューターでファイルを作成した場合は、そのファイルを展開するコンピューターのロケールを日本語に設定する必要があります。 ファイルとコンピューターの設定が一致しない場合は、BAM 管理ユーティリティの実行に使用するコンピューターを適切なロケールに切り替え、ユーティリティを実行する前にコンピューターを再起動する必要があります。  
  
> [!NOTE]
>  すべての言語で同じコード ページを使用している場合、または英語を含む 2 種類の言語だけを使用している場合を除いて、BAM 定義 XML ファイルに複数の言語のテキストを含めることはできません。  
  
 コンピューターのロケールの設定を変更する方法については、オペレーティング システムのヘルプを参照してください。  
  
### <a name="to-deploy-a-bam-definition"></a>BAM 定義を展開するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  」と入力して、追跡フォルダーに移動**C:\Program files \microsoft BizTalk Server\<バージョン\>\Tracking**コマンド プロンプトでします。 **Enter**キーを押します。  
  
3.  型**bm 展開すべて-definitionfile:\<BAM 定義ファイル\>**です。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)