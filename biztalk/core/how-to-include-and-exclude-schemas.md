---
title: スキーマを含めたり除外したりする方法 |Microsoft Docs
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
ms.openlocfilehash: e05cdb76ce64fae8b75b212711e805c04ac473a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384946"
---
# <a name="how-to-include-and-exclude-schemas"></a>スキーマを含めたり除外したりする方法
スキーマ ファイルは、BizTalk プロジェクトのフォルダーに存在でき、そのプロジェクトに含まれません。 このようなスキーマは、プロジェクトから除外すると言います。 BizTalk プロジェクトをビルドするときに、除外されたスキーマはコンパイルされません。 このトピックでは、BizTalk プロジェクトで、除外されたスキーマを含めると、スキーマを BizTalk プロジェクトから除外するために必要な手順について説明します。  
  
### <a name="to-include-a-schema-in-a-biztalk-project"></a>BizTalk プロジェクトにスキーマを含める  
  
1.  ソリューション エクスプ ローラーで、プロジェクト フォルダーに含まれるスキーマを含む BizTalk プロジェクトを開きます。  
  
2.  すべてのファイルが既に表示されていない場合で、**プロジェクト**] メニューのをクリックして **[すべてのファイル**します。  
  
3.  ソリューション エクスプ ローラーで、除外されたスキーマに含めるをクリックするを右クリックして**プロジェクトに含める**します。  
  
     ソリューション エクスプ ローラーで除外されていたスキーマのアイコンは、空のアウトラインから通常のスキーマ アイコンに変わります。  
  
4.  必要に応じて、**プロジェクト**] メニューのをクリックして **[すべてのファイル**をプロジェクトに含まれていないプロジェクト フォルダー内のすべてのファイルを非表示にします。  
  
### <a name="to-exclude-a-schema-from-a-biztalk-project"></a>スキーマを BizTalk プロジェクトから除外するには  
  
-   ソリューション エクスプ ローラーで、クリックして、除外するスキーマを右クリックして**プロジェクトから除外**します。  
  
     スキーマは、BizTalk プロジェクトから除外されます。  
  
    > [!NOTE]
    >  スキーマをプロジェクトから除外すると、スキーマは、ファイル システムからは削除されません。 ただし、プロジェクトをビルドするときに、スキーマは含まれません。 プロジェクト フォルダーに切り替えることで除外するファイルを表示するかどうかを選択することができます、 **[すべてのファイル**ソリューション エクスプ ローラー] ウィンドウの上部にあるツールです。  
  
    > [!NOTE]
    >  スキーマ ファイルをプロジェクトから削除するほか、ファイル システムからスキーマを削除する場合は、スキーマを削除する必要があります。 スキーマを削除する方法についての詳細については、次を参照してください。[スキーマの削除](../core/how-to-delete-schemas.md)します。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマの管理](../core/managing-schemas-within-projects.md)