---
title: 一般的な質問と回答のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2f89d92-0a97-4017-8b8e-6afd8b20eaf4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a47cfd0bc1d2de1ad044712c12b97260981e610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010651"
---
# <a name="general-troubleshooting-questions-and-answers"></a>一般的なトラブルシューティングに関する質問と回答
このトピックでは、質問と回答は、BizTalk マッパーに関する問題を解決するためには。  
  
## <a name="how-do-i-specify-xslt-output-settings"></a>XSLT 出力の設定を指定する方法を教えてください。  
 BizTalk マッパーで、XML 宣言を含めるかどうかを指定し、出力インスタンス データで使用するエンコードを制御できます。  
  
#### <a name="include-or-exclude-an-xml-declaration"></a>含めるか、XML 宣言を除外  
  
1.  グリッド ビューで、マッパー グリッドをクリックします。 **プロパティ**ウィンドウ グリッドのプロパティを表示します。  
  
2.  ドロップダウン リストで、 **XML 宣言の省略**プロパティで、 **[はい]** 、XML 宣言を省略するか選択**いいえ**XML 宣言を省略するされません。  
  
#### <a name="set-encoding-for-output-instance-data"></a>出力インスタンス データのエンコーディングを設定します。  
  
1.  グリッド ビューで、マッパー グリッドをクリックします。 **プロパティ**ウィンドウ グリッドのプロパティを表示します。  
  
2.  ドロップダウン リストで、 **XSLT エンコード**出力インスタンス データに使用するプロパティ、文字セットを選択します。  
  
## <a name="how-do-i-create-multipart-mappings"></a>マルチパート マッピングを作成するにはどうすればよいですか。  
 同時に使用される複数のマップがある場合は、オーケストレーションを使用してそれらを結合する必要があります、**変換**図形を同時にテストします。 BizTalk マッパーで一度にテストできるのは 1 つのマップだけです。  
  
## <a name="why-isnt-my-database-functoid-working"></a>データベース Functoid が動作しないのはなぜですか。  
 データベース functoid**データベース検索**と**値抽出**; のエラー情報を直接返さないではなく、情報をキャプチャしを指定、**エラーを返す** functoid、マップで使用します。 使用することができます、**エラーを返す**functoid は次のシナリオと同様に、エラー検出のため。  
  
- マップの場合に、**データベース検索**または**値抽出**functoid は期待どおりに動作するいないとしています。 エラー メッセージを表示するには、この Functoid を出力スキーマのフィールドに一時的にマップしてください。  
  
- データベース操作が失敗したときに、アプリケーションで別のメッセージ内容が要求された場合。 使用することができます、**エラーを返す**functoid をエラーが検出され、ダウン ストリーム アプリケーションが適切な方法で対応できるように、エラー メッセージを代替構造にマップします。  
  
  実行時にしか検出されないエラーを回避することを確認最初のパラメーター、**エラーを返す**functoid の出力を**データベース検索**functoid とその他の functoid での出力ではない、データベースのカテゴリ。  
  
  使用しての詳細については、**エラーを返す**functoid (サンプルを含む) を参照してください、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="why-is-my-map-failing-when-calling-my-custom-functoid"></a>カスタム Functoid を呼び出すとマップで障害が発生するのはなぜですか。  
 マップでカスタム Functoid を呼び出せるようにするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターのグローバル アセンブリ キャッシュ (GAC) にそれらのカスタム Functoid をインストールしておく必要があります。 カスタム Functoid を含むアセンブリが署名されており、GAC に配置されていることを確認してください。 また、アセンブリを "%BTSINSTALLPATH%\Developer Tools\Mapper Extensions" フォルダーにコピーします。  
  
 アセンブリを GAC にインストールの詳細については、[GAC でアセンブリのインストール](../core/assembly-installation-in-the-gac.md)を参照してください。 GAC にインストールされたアセンブリを表示するには、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] のインストール ディレクトリの Assembly ディレクトリに移動します。  
  
## <a name="see-also"></a>参照  
 [マップのトラブルシューティング](../core/troubleshooting-maps.md)