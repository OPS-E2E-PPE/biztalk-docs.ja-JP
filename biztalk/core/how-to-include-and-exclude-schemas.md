---
title: スキーマを含めたり除外したりする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9206458-e5d6-48d7-87a6-9471ba60dca7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dfa1f610cef6e67f17ca14737c6ca853dd5cd16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254346"
---
# <a name="how-to-include-and-exclude-schemas"></a>スキーマを含めたり除外したりする方法
BizTalk プロジェクト フォルダーに存在するスキーマ ファイルが、実際にはそのプロジェクトに追加されていない場合があります。 このようなスキーマを、プロジェクトから除外されたスキーマといいます。 除外されたスキーマは、BizTalk プロジェクトのビルド時にコンパイルされません。 このトピックでは、特定のスキーマを BizTalk プロジェクトから除外したり、除外したスキーマを BizTalk プロジェクトに追加したりするための手順について説明します。  
  
### <a name="to-include-a-schema-in-a-biztalk-project"></a>BizTalk プロジェクトにスキーマを追加するには  
  
1.  ソリューション エクスプローラーで、プロジェクト フォルダーに追加するスキーマが格納されている BizTalk プロジェクトを開きます。  
  
2.  すべてのファイルが既に表示されていない場合、、**プロジェクト** メニューのをクリックして**すべてのファイル**です。  
  
3.  ソリューション エクスプ ローラーで、をクリックし、含める除外されたスキーマを右クリックして**プロジェクトに含める**です。  
  
     ソリューション エクスプローラーで、それまで除外されていたスキーマのアイコンが、通常のスキーマ アイコンに変化します。  
  
4.  必要に応じて、**プロジェクト**] メニューのをクリックして **[すべてのファイル**は含まれていないプロジェクトで、プロジェクト フォルダー内のすべてのファイルを非表示にします。  
  
### <a name="to-exclude-a-schema-from-a-biztalk-project"></a>スキーマを BizTalk プロジェクトから除外するには  
  
-   ソリューション エクスプ ローラーで、をクリックして、除外するスキーマを右クリックして**プロジェクトから除外**です。  
  
     スキーマが BizTalk プロジェクトから除外されます。  
  
    > [!NOTE]
    >  スキーマをプロジェクトから除外しても、そのスキーマがファイル システムから削除されるわけではありません。 プロジェクトをビルドしたときに、スキーマが追加されないというだけです。 プロジェクト フォルダーに切り替えることにより除外するファイルを表示するかどうかを選択することができます、 **[すべてのファイル**ソリューション エクスプ ローラー] ウィンドウの上部にあるツールです。  
  
    > [!NOTE]
    >  スキーマ ファイルをプロジェクトから除外するだけでなく、ファイル システムからも削除したい場合は、スキーマを直接削除する必要があります。 スキーマの削除の詳細については、次を参照してください。[スキーマの削除](../core/how-to-delete-schemas.md)です。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md)